# Chapter 13: Refining Gold in the Mud and the Great Wall of Steel

1992. Boston.

Marc Raibert stood in the laboratory at MIT, staring at a mechanical leg that was hopping.

He was a professor at MIT, researching bionic robots. His team developed a single-leg hopping robot that could maintain stability through active balance. This was a breakthrough in robot control.

In 2005, Raibert left MIT and founded Boston Dynamics. His goal was to develop robots that could move like animals.

Boston Dynamics' first product was BigDog, a quadruped robot used to carry equipment for soldiers. It could walk on rough terrain and stand up after being pushed over.

In 2013, Boston Dynamics released Atlas, a bipedal humanoid robot. It could walk, jump, and do backflips. The video went viral on YouTube, and people marveled at its agility.

It stood up.

It stood up.

But Boston Dynamics never found a business model. It was successively acquired by Google and SoftBank, and finally by Hyundai Motor in 2020.

---

**Meanwhile, on the other side of the Earth.**

2016. Shenzhen.

Wang Xingxing founded Unitree in Shenzhen.

He was a robotics enthusiast who had developed quadruped robots during college. He found that Boston Dynamics' robots were too expensive, costing hundreds of thousands of dollars. He wanted to make a cheap quadruped robot that ordinary people could afford.

In 2017, Unitree released Laikago, a quadruped robot priced at one-tenth of Boston Dynamics'.

In 2021, Unitree released Go1, a consumer-grade quadruped robot priced at only 16,000 yuan. It could accompany running, carry items, and be used for programming education.

Unitree's success marked the rise of China's robotics industry: using extreme supply chain efficiency to turn expensive cutting-edge technology into cheap consumer goods.

Costs came down.

Robots became affordable.

---

What is embodied AI?

It is AI with a body. Large language models are the "brain," and robots are the "body." The brain thinks, the body acts.

The core challenge of robots is motion control.

Traditional robot control uses "model predictive control." Engineers build mathematical models of robots, design controllers, and make robots move along predetermined trajectories.

But this method has limitations. Models are approximations, and the real world is complex. When robots walk on uneven ground, are pushed by external forces, or have changing loads, models may fail.

The new method is "reinforcement learning." Robots try repeatedly in simulation environments and learn how to move. They don't need precise models; they only need to define reward functions: the farther and more stable they walk, the higher the reward.

Reinforcement learning allows robots to learn more flexible ways of moving. Boston Dynamics' Atlas can do backflips, trained through reinforcement learning.

But reinforcement learning also has problems. There are differences between simulation environments and the real world; skills learned in simulation may not transfer to the real world. This is called the "sim-to-real gap."

Solutions include:

Domain randomization: Randomly changing environmental parameters in simulation, allowing robots to learn to adapt to various situations.

System identification: Measuring the robot's physical parameters in the real world and updating the simulation model.

Online adaptation: Robots continuously learn in the real world and adapt to new environments.

---

Robots need to perceive the environment to act within it.

Visual perception: Cameras capture images, and AI models recognize objects, estimate distances, and understand scenes. Large language models can help robots understand natural language instructions.

Tactile perception: Force sensors and tactile sensors allow robots to perceive contact forces and object textures. This is crucial for fine manipulation.

Navigation: Robots need to know their location in the environment and plan paths to reach targets. SLAM technology allows robots to build maps and locate themselves while moving.

Navigation can be divided into two levels:

Global navigation: Planning a path from the starting point to the destination, avoiding obstacles. Similar to car navigation.

Local navigation: Avoiding dynamic obstacles while moving and adjusting steps. Similar to the subconscious avoidance when humans walk.

---

Robot hands are another challenge.

The human hand has 27 degrees of freedom and can perform various fine operations. Robot hands usually have only a few degrees of freedom, far less flexible than human hands.

Parallel grippers: The simplest robot hands, with only two fingers, can grasp objects. Suitable for industrial scenarios but not for complex operations.

Multi-fingered hands: Designed to imitate human hands, with three to five fingers, capable of more complex operations. But high control difficulty and high cost.

Soft hands: Use flexible materials that can adapt to objects of different shapes. But low precision, not suitable for fine operations.

Learning-based manipulation: Using reinforcement learning or imitation learning to teach robots manipulation skills.

By 2023, robot manipulation remains an open research problem.

---

In 2023, I first saw Unitree's Go1.

It was at a tech exhibition. Go1 was walking in the exhibition hall, following its owner. When the owner ran, it ran; when the owner stopped, it stopped.

I squatted down and touched its metal shell. It was cold and hard, completely different from a real dog. But its movements were so natural that I almost forgot it was a machine.

The exhibitor told me that Go1 could carry 3 kilograms, accompany running, and be used for programming education. The price was only 16,000 yuan, cheaper than a purebred dog.

I thought: the era of robots has really arrived.

---

**Epilogue: 2026**

Tesla released Optimus, a humanoid robot.

It can walk, grasp objects, and perform simple tasks. Musk said that Optimus' price would be less than $20,000, cheaper than a car.

Musk's vision is: when robots can do all the work humans don't want to do, humans can focus on creative work.

But this vision faces challenges. Technical maturity, cost control, safety assurance—all are unknowns.

The destiny of code depends on the people holding the keyboard.

And the next chapter of the story has just begun.