Current Usages
No Loyalty ID
Create a new account with PPSRX
Stage URL: https://www-stage.ppsrx.com/health/pps?redirectUrl=/rx/dashboard
Requires validated email: https://mail.tm
Log into the app with your newly created PPSRX account
You'll be prompted to enter a Postal Code, use any
Watch Charles for the call to the preferred store endpoint
MSL - POST https://mobile-stage.kroger.com/mobileprofile/api/v1/preferred-store/Kroger
Apex - PUT https://mobile-stage.kroger.com/mobileatlas/v1/customer-profile/v1/preferences/store
Validate that the user's Preferred Store was setup in KCI https://ecsb-stage.kroger.com/kci/
Cross-banner
Create an account with a Kroger banner (let's say Kroger for instance)
Log in with that Kroger account on another banner
You'll be prompted to enter a Postal Code, use any
Watch Charles for the call to the preferred store endpoint 
MSL - POST https://mobile-stage.kroger.com/mobileprofile/api/v1/preferred-store/Kroger
Apex - PUT https://mobile-stage.kroger.com/mobileatlas/v1/customer-profile/v1/preferences/store
Validate that the user's Preferred Store was setup in KCI https://ecsb-stage.kroger.com/kci/
CIAM
It appears in the not-enabled, half-implemented CIAM Create Account flow we are also setting preferred store. We need to revisit this as part of the revamped Create Account flow.

Edge Cases
If you want to test the limits of this endpoint, try using a zip code far away from where these stores operate. For example use some east coast zip codes in a Ralph's banner. When the Apex toggle is enabled for preferred store (`NarutoPreferredStoreApexActive`) then we should find stores within a 3000 mile radius of any zip code which should work for most of the country.

Practically speaking, this doesn't always work. Most often, in the edge cases, the store search returns an Ocado shed or some 'invalid' location first. Without any logic to find valid locations in the list, preferred store can just fail in these cases.

Proposed Solution
The only time we call our endpoint to set preferred store is for the 'No Loyalty ID' and 'Cross-banner' situations. In these situations we need a way to get a Store ID/Div Number combination that works and is the 'best guess' for the user's closest location. The priority is any working store, not necessarily the best store for the customer.

Options:

Use the x-laf-object header to pull the 'listing key' from the PICKUP modality. This is the best approximated guess for a PICKUP store for a user.
If the PICKUP 'listing key' is an invalid store (check some basic checks like Ocado sheds, etc.), then use the /stores/v2/locator call to try to get any location within 3000 miles for the current banner. If the store returned there.
Optional/proposed: If the store returned from the store search is an invalid store, provide some dummy placeholder store
