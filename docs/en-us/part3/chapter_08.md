# Chapter 8: The Crazy Game of the Man in the Leather Jacket

1999. Santa Clara, NVIDIA headquarters.

Thirty-six-year-old Jensen Huang stood in the conference room, facing a group of investors. He wore his signature black leather jacket—that jacket he wore for ten years, in conference rooms in Santa Clara, on stage at Computex in Taipei, in the office sending emails at 3 AM. That jacket was like his second skin.

He spoke rapidly, his gestures exaggerated, like a rock star performing on stage. The investors were surprised or thoughtful, some shaking their heads, some nodding.

Jensen Huang was pitching a crazy idea: making dedicated graphics cards for gamers.

"Competition makes everyone better," he liked to say. "Without competition, there is no progress."

His work habits were famously crazy. At 3 AM, when all of Silicon Valley was asleep, his emails would appear in employees' inboxes. He was either working or thinking about work. There was a simple folding bed in his office; when working late, he would sleep right at the company.

At that time, the computer graphics market was dominated by companies like 3dfx, ATI, and S3. Their products were "3D accelerator cards," specifically for processing 3D graphics. But each company's API (Application Programming Interface) was different; game developers had to write different code for each graphics card.

Jensen Huang's idea was: make a graphics card that supports all APIs and provide unified development tools.

In August 1999, NVIDIA released the GeForce 256. It was called "the world's first GPU" (Graphics Processing Unit).

The breakthrough of GeForce 256 was: it moved "Transform and Lighting" (T&L) from the CPU to the GPU. Before this, 3D graphics geometry transformations and lighting calculations were done by the CPU; the GPU only handled pixel rendering. GeForce 256 put all these calculations on the GPU, freeing up the CPU.

Gamers went crazy. The GeForce 256's performance was more than twice as fast as competitors. NVIDIA's stock price soared.

But Jensen Huang's goal went beyond this. He saw another potential of GPUs: general-purpose computing.

---

**Meanwhile, on the other side of the Earth.**

1987. Hsinchu, Taiwan.

Morris Chang wore a yellow hard hat, standing at the construction site of TSMC. Behind him were scaffolding and cranes; before him was a rising wafer fab. He held chip design drawings in his hand, his gaze firm.

He was the founder of TSMC (Taiwan Semiconductor Manufacturing Company). Before that, he was Senior Vice President of Texas Instruments, in charge of the semiconductor business. He had worked at Texas Instruments for 25 years, rising from an ordinary engineer to Senior Vice President, achieving fame and success. He could have enjoyed his retirement in the United States.

But he chose to return to Taiwan.

The Taiwan government gave him full support: land, funding, policy. But more importantly, he saw a historic opportunity—chip foundry.

Before the 1980s, chip companies were all IDMs (Integrated Device Manufacturers): they designed chips themselves and manufactured chips themselves. Intel, Texas Instruments, and Motorola were all IDM models.

But the IDM model had a problem: building a wafer fab cost billions of dollars. Only large companies could afford it. Small companies, even with good chip designs, couldn't manufacture them.

Morris Chang's idea was: establish a dedicated chip foundry to manufacture chips for other companies. Fabless chip design companies only needed to design chips; they didn't need to build factories.

This was a revolutionary idea. But at the time, no one believed it was feasible.

With the support of the Taiwan government, Morris Chang founded TSMC. He looked for customers everywhere, but large companies were unwilling to outsource chip manufacturing to a small company.

The turning point came in the 1990s. Fabless companies like NVIDIA, Qualcomm, and Broadcom rose; they needed foundries. TSMC became their first choice.

By 2000, TSMC became the world's largest chip foundry.

---

GPU is one of the most important inventions in computer history. It not only changed gaming but also changed artificial intelligence.

### Parallel Computing: The Essence of GPU

The fundamental difference between CPU and GPU is: CPU excels at serial computing, GPU excels at parallel computing.

**CPU**: Has a small number of powerful cores (usually 4-64), each capable of executing complex instructions. CPU excels at handling logic judgments, branch jumps, and operating system scheduling.

**GPU**: Has a large number of simple cores (usually thousands), each only capable of executing simple instructions. GPU excels at handling large numbers of similar computing tasks, such as image rendering.

Image rendering is a typical parallel computing problem. There are millions of pixels on the screen; each pixel's color needs to be calculated independently. These calculations are similar and independent, perfectly suited for GPU.

GPU architecture is SIMD (Single Instruction, Multiple Data): one instruction simultaneously acts on multiple data. For example, one "addition" instruction can simultaneously calculate the sum of hundreds of pairs of numbers.

The cost of this architecture is: GPU is not good at handling branches and jumps. If code has large amounts of if-else, GPU efficiency drops significantly.

### CUDA: The Key to General-Purpose Computing

In 2006, NVIDIA released CUDA (Compute Unified Device Architecture).

CUDA is a programming model that allows developers to write GPU programs using C language. Before this, GPUs could only be used for graphics rendering; developers needed to use graphics APIs (such as OpenGL, DirectX) to indirectly use GPUs.

CUDA made the GPU a general-purpose parallel computing device. Developers could use GPUs to process any parallelizable task: scientific computing, financial modeling, password cracking, machine learning.

Jensen Huang later recalled: "CUDA was the riskiest decision we ever made. We spent ten years and billions of dollars before it succeeded."

CUDA was not successful at first. Developers were not accustomed to GPU programming; academia was skeptical of GPUs. NVIDIA had to donate GPUs to universities, hold programming competitions, and cultivate developer communities.

The turning point came in 2012.

### Deep Learning: The Killer App for GPU

In 2012, AlexNet won the ImageNet image recognition competition, with accuracy 10 percentage points higher than second place.

AlexNet is a deep convolutional neural network developed by Alex Krizhevsky, Ilya Sutskever, and Geoffrey Hinton. Its breakthrough: using GPUs to train neural networks.

Before AlexNet, neural network training mainly used CPUs. But CPU computing power was limited; training a deep network took weeks or even months.

AlexNet used two NVIDIA GTX 580 GPUs, reducing training time to days. This proved the huge advantage of GPUs in deep learning.

Since then, deep learning researchers began using GPUs extensively. NVIDIA GPUs became the standard configuration for AI research.

Computing power exploded.

Jensen Huang keenly seized this opportunity. He adjusted NVIDIA's strategy, making AI the core application scenario for GPUs.

In 2016, NVIDIA released Pascal architecture GPUs, specifically optimized for deep learning. In 2017, NVIDIA released Volta architecture, introducing Tensor Cores specifically for matrix operations—the core computation of deep learning.

By 2020, NVIDIA occupied over 90% of the AI chip market. The moat was dug.

---

The rise of GPUs challenged Intel's dominance.

### Intel's Miss

Intel was the dominant player in the CPU market. In the PC era, Intel's x86 architecture ruled the personal computer and server markets.

But Intel missed the mobile era. The ARM architecture dominated the smartphone market; Intel's Atom processor failed.

Intel also missed the AI era. Intel believed CPUs were powerful enough and didn't need dedicated accelerators. When GPUs rose in the AI field, Intel was caught off guard.

Intel tried to catch up. In 2016, Intel acquired Nervana, an AI chip startup. In 2017, Intel acquired Mobileye, an autonomous driving chip company. In 2019, Intel acquired Habana Labs, another AI chip company.

But these acquisitions didn't produce the expected results. Intel's AI chip product line was chaotic, with performance inferior to NVIDIA GPUs.

By 2020, NVIDIA's market cap exceeded Intel's. A company making graphics cards was worth more than a company making CPUs.

The dynasty changed.

### NVIDIA's Moat

NVIDIA's moat was not just hardware but software ecosystem.

CUDA was NVIDIA's biggest moat. Over more than a decade, developers built countless AI frameworks and tools based on CUDA: TensorFlow, PyTorch, MXNet... Almost all mainstream deep learning frameworks prioritized CUDA support.

If a company wanted to develop AI applications, the simplest choice was to use NVIDIA GPUs. Using other hardware required re-adapting software, with huge costs.

NVIDIA also developed software libraries like cuDNN and TensorRT, optimizing deep learning training and inference. These libraries were deeply bound to NVIDIA hardware, further deepening the moat.

Competitors tried to break NVIDIA's monopoly.

**AMD**: Launched ROCm (Radeon Open Compute), an open-source GPU computing platform. But ROCm's software ecosystem was far less mature than CUDA.

**Google**: Developed TPU (Tensor Processing Unit), specifically for TensorFlow. But TPUs were mainly used internally at Google, with limited external services.

**Huawei**: Developed the Ascend series of AI chips. But affected by US sanctions, Ascend chip production was limited.

By 2023, NVIDIA remained the absolute dominant player in the AI chip market.

---

NVIDIA designs GPUs but doesn't manufacture them. GPU manufacturing depends on TSMC.

### TSMC: The King of Chip Manufacturing

Chip manufacturing is one of the most complex industrial processes in human history.

A GPU chip has tens of billions of transistors. Each transistor is only a few nanometers in size. The manufacturing process requires hundreds of steps; any mistake in any step, and the entire wafer is scrapped.

TSMC is the world's most advanced chip manufacturer. It was the first to achieve mass production of 7nm, 5nm, and 3nm processes.

NVIDIA's GPUs are manufactured by TSMC. NVIDIA designs chips, sends design files to TSMC, and TSMC manufactures the chips and delivers them to NVIDIA.

This division of labor model (Fabless + Foundry) has become the mainstream of the semiconductor industry. Apple, Qualcomm, AMD, and NVIDIA are all Fabless; TSMC and Samsung are Foundries.

TSMC's success stems from Morris Chang's strategic vision and execution.

**Continuous Investment**: Chip manufacturing is a capital-intensive industry. TSMC invests tens of billions of dollars annually in building new factories and developing new processes. Even during industry downturns, TSMC did not stop investing.

**Customer Orientation**: TSMC doesn't compete with customers. It only does foundry, not chip design. This reassures customers to hand over designs to TSMC.

**Technology Leadership**: TSMC works closely with equipment vendors like ASML and Applied Materials, being the first to introduce the most advanced manufacturing equipment.

By 2020, TSMC occupied over 50% of the global chip foundry market. In the advanced process (7nm and below) market, TSMC's share exceeded 90%.

### ASML: The Monopolist of Lithography Machines

The core equipment of chip manufacturing is the lithography machine. ASML occupies over 80% of the high-end lithography machine market. EUV (Extreme Ultraviolet) lithography technology has a wavelength of 13.5 nanometers, enabling 7nm and below processes.

EUV development took over 20 years, with investment exceeding $10 billion. ASML is the only company to successfully mass-produce EUV lithography machines.

The price of one EUV lithography machine exceeds $100 million; only dozens are produced globally each year. TSMC, Samsung, and Intel are the main customers of EUV lithography machines.

ASML's monopoly stems from its unique technical accumulation and supply chain integration. EUV lithography machines have over 100,000 parts, from hundreds of suppliers worldwide. ASML integrates these parts into a precision system that any competitor would find difficult to replicate.

### Energy: The Invisible Foundation of Computing Power

Chip manufacturing and data center operations both require massive amounts of electricity.

**TSMC's Energy Consumption**: An advanced process wafer fab consumes over 7 billion kWh annually, equivalent to the electricity consumption of a small city. TSMC's electricity consumption in 2023 accounted for 7.2% of Taiwan's total. Taiwan had to accelerate offshore wind, gas, and storage buildout to meet TSMC's expansion needs.

**Data Center Energy Consumption**: Training GPT-4 consumed electricity equivalent to 5,000 US households' annual consumption. NVIDIA H100 GPU power consumption is 700W; one server with 8 GPUs exceeds 5kW. A data center with 100,000 servers consumes over 5 billion kWh annually.

**Energy Layout Becomes a Strategic Resource**:
- US data centers are concentrated in Virginia (cheap electricity, close to Washington) and Oregon (abundant hydropower)
- China's "East Data West Computing" project builds data centers in Guizhou and Inner Mongolia—where there is cheap hydropower and wind power
- Microsoft signed contracts with nuclear fusion companies; Google builds solar power plants next to data centers

The competition for computing power is essentially a competition for energy. Whoever masters cheap, clean, and stable electricity will have the advantage in the AI era.

---

In the summer of 2021, I attended an AI conference in Silicon Valley. In the exhibition hall, NVIDIA's booth was the most eye-catching—dozens of A100 servers lined up, the fan hum like a low engine. I reached out and touched the metal surface of the heat sink; it was so hot I jerked my hand back. An engineer said: "This row can process a library per second." At that moment, computing power was no longer a concept to me; it was temperature.

In the summer of 2020, I walked into an AI company's server room. Opening the door, cold air hit me, and a low hum filled my ears. Rows of racks were densely packed with black card slots filled with GPUs—newly launched A100s and prior-generation V100s, each worth tens of thousands of dollars. Lights flickered on metal heat sinks, like some kind of industrialized ganglion. At that moment, I realized: this silent hardware was reshaping human cognition of intelligence at a speed of trillions of floating-point operations per second. Computing power is not abstract; it is a physical existence that can be seen, touched, and heard.

2015 was the year of the deep learning explosion.

At that time, GPUs were just beginning to be widely used for deep learning training. A simple convolutional neural network took a week to train on CPU; with NVIDIA GTX Titan X GPU, training time was reduced to one day. One graphics card was equivalent to the computing power of dozens of CPUs.

NVIDIA doesn't just sell hardware; it also sells software. CUDA, cuDNN, TensorRT... NVIDIA has built a complete AI development ecosystem. This is NVIDIA's core competitiveness: deep integration of hardware and software.

NVIDIA's GPUs depend on TSMC's manufacturing; TSMC's manufacturing depends on ASML's lithography machines. This is a globalized supply chain: the US designs chips, Taiwan manufactures chips, the Netherlands provides equipment, and global consumers use chips.

But this supply chain is being torn apart by geopolitics.

In 2019, the US put Huawei on the entity list, prohibiting US companies from selling chips and technology to Huawei. TSMC was forced to stop manufacturing chips for Huawei.

In 2020, the US further tightened restrictions, prohibiting any company using US technology from selling chips to Huawei.

In 2022, the US banned the export of advanced chip manufacturing equipment to China. ASML was prohibited from selling EUV lithography machines to China.

These sanctions have caused huge shocks to China's semiconductor industry. Huawei's Kirin chips cannot be produced; Chinese AI companies struggle to obtain NVIDIA's high-end GPUs.

China has begun vigorously developing its own semiconductor industry. SMIC, YMTC, Huawei HiSilicon, and other companies have increased R&D investment. But catching up takes time.

Computing power has become a strategic resource.

Whoever masters computing power masters AI. Whoever masters AI masters the future.

NVIDIA, TSMC, and ASML—these three companies hold the lifeline of global computing power. Their decisions affect the global technology landscape.

This is a kind of power. And power needs to be examined.

---

**Epilogue: May 29, 2023**

Jensen Huang stood on the Computex stage in Taipei in his black leather jacket, showcasing data-center products for generative AI. The H100 had been announced in 2022 and was among the most sought-after AI accelerators; he had said at GTC in March 2023, "We are at the iPhone moment of AI."

H100 chips cost tens of thousands of dollars each, and customers queued for months.

OpenAI trained GPT-4 on A100 clusters before scaling H100 deployments. Microsoft uses H100 to build Azure AI services. Tesla uses H100 to train autonomous driving models.

NVIDIA's stock price soared. In 2023, NVIDIA's market cap broke through $1 trillion, becoming the world's most valuable chip company.

Jensen Huang's net worth exceeded $30 billion, placing him among the world's wealthiest executives.

Thirty years ago, he made graphics cards for gamers. Thirty years later, he makes brains for the AI era.

The destiny of code is sometimes grander than the code itself.