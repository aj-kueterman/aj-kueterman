# What MacBook to Buy for Android Development?
Now that there are new, M1-series MacBook Pros, a lot of developers may be looking to finally upgrade from their Intel-based MacBooks.

Considering the memory and GPU considerations of Android development, the configuration I would suggest would be either:

## Perfect World
These configurations bump up GPU performance and add Memory, both which would make things run even smoother for Android dev, but are probably overkill for now. If anything, this just guarantees a longer effective lifetime of these machines, so depending on what the usual active lifetime of our MacBooks are you may or may not want to invest the extra $600 per machine.

### 14" MacBook Pro
* Apple M1 Max with 10-core CPU, 24-core GPU, 16-core Neural Engine
* 64GB unified memory
* 1TB SSD storage
* **$3,499.00**

### 16" MacBook Pro
* Apple M1 Max with 10-core CPU, 24-core GPU, 16-core Neural Engine
* 64GB unified memory
* 1TB SSD storage
* **$3,699.00**

## Recommended
Gabriel Peal, a GDE and former Google engineer [recommends this 14" configuration](https://gpeal.medium.com/the-m1-pro-for-android-engineers-a144093aa1ec) and I included the respective 16" configuration as well.

I think this hits the sweet spot of performance / cost. 32 GB is a memory minimum at this point for Android Dev, but should give enough headroom to fly for the next few years at least. The 10 core Pro CPU will make a difference over the 8 core Pro for Gradle builds, and the 16 core GPU over the 14 will do the same for Android Emulator performance.

### 14" Macbook Pro
* Apple M1 Pro with 10-core CPU, 16-core GPU, 16-core Neural Engine
* 32GB unified memory
* 1TB SSD storage
* **$2,899.00**

### 16" MacBook Pro
* Apple M1 Pro with 10-core CPU, 16-core GPU, 16-core Neural Engine
* 32GB unified memory
* 1TB SSD storage
* **$3,099.00**

## Anecdotal Evidence
Memory pressure graph on current 15" MBP 16GB memory.

<img width="852" alt="Screen Shot 2021-10-29 at 3 30 48 PM" src="https://user-images.githubusercontent.com/88003213/139491817-2aadfef7-208a-48c4-b2fa-691a7804e038.png">
<img width="852" alt="Screen Shot 2021-10-29 at 3 34 17 PM" src="https://user-images.githubusercontent.com/88003213/139492206-8a4c42dc-e103-4fb3-bf92-9e84748c49b5.png">

## Other Thoughts

Remember that often times we aren't just single-lane developers. Native devs might have Android Studio and Xcode open at the same time, even running Emulators and Simulators side-by-side. The ability to have multiple development environments open at the same time is hugely helpful in building native apps with parity and when integrating with services, where you may have 3 IDE's open to compare Android to iOS and understand the server side code you're integrating with.

Having 3 IDE's open, running a local service and running 2 emulators might sound excessive, and it might happen somewhat rarely, but the ability to do so without grinding your Mac to a halt is a real boon.

Every minute shaved off a build, rendering a screen in our IDE, running a device adds up. The ability to practically run our builds on many devices at once means we can be more consistent and iterate faster.

Long story short, consider what workflows are really enabled with a faster machine, not just the headache's we're trying to avoid by bumping up to the next minimum specs.
