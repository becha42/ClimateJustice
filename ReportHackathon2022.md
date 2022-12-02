#    QUBITS FOR THE CHILDREN

Realizing a sustainable quantum internet for the smallest/future researchers

Authors: 

- Jasper van de Kraats 
- Swantje Kastrup  
- Robert de Keijzer  
- Zhichao Guo  
- María Gragera Garcés 
- Ed Kuijpers
- Vesna Manojlovic


# INTRODUCTION

## What is sustainability?

With the progress of a quantum internet also sustainability should be considered.
The sustainability of a system is influenced by different factors: the ecological footprint and social impacts like social and environmental justice or human and labour rights [34]. But also software maintainability and portability is a factor.
With this project we would like to focus on the ecological impact of the quantum internet and how it could be measured.
The ecological sustainability of a system is influenced by the following factors that have to be considered when comparing systems [27, 28]:

- Environmental impact of the production with regard to the materials needed, energy consumption, waste
- Distribution of the system (e. g. is shipping necessary?)
- What is the life span of the system?
- What are the operation costs?
- Is it possible to recycle (at least parts of) the system?


In order to evaluate the sustainability of the quantum internet it makes sense to look at the devices that are used for building a quantum internet individually (additionally to classical ones):

- Quantum computers
- QKD (quantum key distribution) devices
- Quantum repeaters / routers for building communication channels
- Application Scenarios and standardization(IETF)


## How is the sustainabliliy of classical computing evaluated?

Without going too much in detail, the probably most well known criterion used for evaluating the sustainability of current high perfomance computing systems is the energy efficiency of the system measured by the number of FLOPS per Watt (there is a ranking of the Green500 supercomputers in the world [29]).
There are different ways to reduce the power consumption, one is optimizing the cooling technology used, for example by using warm water cooling (a technology developed by IBM).
But also the heat produced by the system is a topic that has a high impact which is not directly measured when looking at FLOPS per Watt, but the heat must not be wasted: It might instead be used for heating buildings, etc.
Also the source of power should be considerd. Are renewables used or e.g coal?
And as a last example of impacts, the use of rare materials for manufacturing should be mentioned.


## Challenges in Quantum vs Classical comparison

A side by side comparison of Quantum and Classical systems is incredibly difficult to perform, for the following reasons:
- Firstly, the nature of quantum and classical information is different in essence. We cannot dirrectly compare a qubit and a bit as they follow different probabilist laws, respond to different effects and mantain differences physically. Therefore computational costs and outputs can only be benchmarked in a case by case manner, and even within specific contexts these comparisons can be questionable as the inputs given to both systems are not equivalent.
- Quantum technologies are still at their infancy, and their performance against more highly developped classical machines is difficult to benchmark. This is especially true at the level on communications and networking, where we have just recently seen some of the first experimental networks come to live. The infancy of these technologies is also directly correlated to low levels of information and scientific research regarding their impact on the environment. 
- The financial costs surrounding quantum information, as well as the hardware restrains make large scale research difficult to perform. Due to the probabilistic nature of quantum elements, large scale research is required to highlit the benefits and power of the technology. The difficulty to perform large scale tests and thus evaluate the real energy consumption costs at scale for the different types of quantum machines only heightens the previous point. 

The challenges to compare Quantum and Classical machines and networks come from the physical nature of the technologies, the infancy of quantum machines and the difficulties surrounding  fair and accessible testing bechmarks. As of today, it is impossible to perform and accurate side by side comparison of both systems. Therefore, through this analysis we have decided to focus on specific elements and properties which we consider define a system as more efficient. These properties have been chosen and weighted based on their impact in current and future techological systems accross the various hardware platforms Quantum computers take. 


# QUANTUM MACHINES

In this section we consider the hardware implementation of qubits from the viewpoint of sustainability.

## Quantum Hardware and Computational requirements
In 2000, theoretical physicist David P. DiVincenzo formulated 5 criteria that formally define a machine capable of performing quantum computation [35]:

- A scalable physical system with well-characterized qubit
- The ability to initialize the state of the qubits to a simple fiducial state
- Long relevant decoherence times
- A "universal" set of quantum gates
- A qubit-specific measurement capability


These 5 are supplemented by two additional criteria that further verify a machines capability to perform quantum communication as well:

- The ability to interconvert stationary and flying qubits
- The ability to faithfully transmit flying qubits between specified locations


The DiVincenzo criteria are, fortunately, quite broad, such that an array of different possible hardware implementations of the concept can be realised. These different implementations, while fundamentally formulated for the same purpose, can have radically different underlying technologies and driving principles. Hence, the question of sustainability also arises naturally in this context. By what metrics should we judge the sustainability and climate impact of different quantum computing hardware, and which currently realised or proposed implementations are most promising in securing a sustainable quantum internet going forward. To this end, we aim to supplement the DiVincenzo criteria with 5 additional criteria, with associated quantifiable metrics, that together allow one to formulate a "sustainability score" for a given hardware implementation. These criteria are formulated from a consideration of both the direct climate impact, such as power draw and required materials, and more indirect notions of sustainability such as modularity and hardware form factor. We first state the 5 categories explicitly:
    

- Power draw density
- Materials
- Maintenance
- Modularity
- Form factor


Together we will refer to this set as the **PMMMF** criteria for a sustainable quantum computer. We will now outline each point in detail.


**1. Power draw density**

A major concern for sustainable quantum computing appears also for classical high performance computing, namely the power draw of the devices involved. This property can vary wildly between different qubit implementations, and is of vital importance for estimating the total power cost of the future quantum internet. A major question is how one properly defines a metric for power draw, that provides both a fair comparison between implementations, and is simultaneously meaningful for comparing with classical high performance computing systems. For the latter, a common way to quantify power efficiency is by measuring the power draw (Watts) per billion floating point operations (GFLOPS) [39]. This metric however, is not very useful for quantum computers, given that floating point operations are not fundamental to quantum computers like they are for classical computers [41]. We instead a propose a more hardware focused metric, which will be well applicable for comparing different architectures. Specifically, we define what we will refer to as a Quantum Computational Power Density (QCPD), denoted as P_d, and quantified as,

P_d = P_p + P_a d^alpha

Here P_p defines what we will refer to as the passive operating power of the device, and gives the power draw required to maintain a single qubit. For most devices, this quantity will encompass the cooling machinery required to maintain stable qubits, and the controlling electronics that allow the device to operate. As one starts to add more qubits and the circuit depth d increases, the active power draw P_a and scaling coefficient alpha start to play a role. These quantities are especially essential for sustainability, since they effectively determine the scaling efficiency of the final quantum internet. In the simple case alpha=1, P_a defines the power cost per qubit operation, which defines the ideal lower bound on the power scaling. For most hardware applications alpha=1 is a fair assumption [18]. If alpha>1, the device possesses what we call unsustainable scaling, making it inherently unsuited for realising a quantum internet. Note of course that alpha might in itself be a function of the number of qubits, depending on the details of the hardware.

**2. Materials**

Whereas classical computers are generally built from widely available silicon, different proposed implementations of quantum computers can rely on rarer materials or complicated material compositions which may have quite different environmental impact. Also, already for classical computers the disposal of materials is a major factor in determining the climate strain [43]. 

We propose to measure the sustainability of the material composition of quantum devices based on three metrics, namely abundance, risk, and cost. Here, abundance quantifies the concentration of a given resource on earth. For composite materials used for example to realise semiconductors, the abundance is defined by the rarest of the elements making up the composite. The sustainability of a material should scale with the abundance, such that use of rarer materials decrease the sustainability score of a given hardware. Although it is not captured by our classification, it is important that the geographic spread of a given resource is also relevant in grading sustainability, and additionally plays an important role in issues of supply chain. This point is beyond the scope of this current work, but we note it as an interesting opportunity for future research [44].

The metric of risk relates to the possible harmful consequences that may result from operating the device, irrespective of whether the device is operated properly. Examples of hardware properties that degrade the metric of risk include: use of materials that pose environmental and/or health related hazards [45], smaller margin of error in using the device, and dangerous internal components in the case that the devices encasing is compromised. Finally, the metric of cost collects the total number of monetary resources required to develop the device. A cheaper device increases accessibility for developing communities, preventing quantum technology to become a privilege of the rich. By minimising cost, quantum computing may act to decrease rather than further economic inequality [46].

**3. Maintenance**

The advent and widespread adoption of personal computers has largely been fueled by an amazing increase in the reliability of classical computational hardware. To secure a sustainable quantum internet in the future it is essential that quantum hardware achieves similar standards of reliability and maintenance cost. We measure the maintenance score of a given hardware using again three independent metrics, which we refer to as lifetime, effort and uptime. The first metric, lifetime, refers to the hardware in typical operation, and measures the total expected time for which a system can run without requiring parts replacements or other specialised repair that strain the climate. Note that the metric of lifetime could be in competition with power draw. A system that uses more energy for cooling might extend the lifetime of its parts, such that one encounters a trade-off that needs to be balanced [47].

The metric of effort instead refers to the point where maintenance is required, i.e. once the lifetime of the hardware has passed. It is then important to quantify the expected labour cost of the repair. For classical computing systems, repairs are usually simple and can often be performed by the user directly. This results in a low effort score, which defines a more sustainable piece of hardware. Given that proposed quantum computing systems can be vastly more complicated, it is important to consider what typical maintenance looks like.

Finally, we judge the maintenance category by also considering the hardware, defined as the percentage of running time the system is available for performing computations. For example, if extensive recalibration of laser optics is required after each hour of actual computation, the device is judged to be less sustainable than an implementation that can run for a week without interruptions.

**4. Modularity**

An important question that will come up once the quantum internet is scaled, is the issue of modularity. Again, we propose a quantifiable measure of modularity by grading the performance of systems with respect to three separate metrics, namely interfaceability, development model, and hardware flexibility. Starting with the first of these, building a quantum internet neccessarily involves a large number of points of contact between different devices. For realising a sustainable quantum internet, it is essential that different devices are designed with universal interfaceability in mind, such that the quantum internet is highly flexible and essentially democratic in its architecture [48, 49]. Explicit examples at the hardware level include universal standards for exchanging data (analogous to the universal serial bus for classical devices) and preventing proliferation of vendor specific proprietary interfaces. For very similar reasons, it is essential that a sustainable quantum internet has an open and democratic development model [50]. On the hardware side, this means that sustainable systems should strive to have universal protocols for data transfer between classical control electronics and the quantum hardware (qubits). The working principle of the system should also be transparent to the user, and obfuscated proprietary hardware design should be discouraged. 

Finally, sustainable quantum hardware should be flexible, specifically with respect to device upgrades following changing computational requirements. If one has built a system of size N, but after some time it turns out a system of size 2N will be required to keep up with user growth, then a sustainable system should be able to re-use the resources already in place for the upgraded hardware. To realise flexibility it is again essential that universal standards are decided on at the start, and then strictly maintained, such that new systems are inherently backwards compatible.

**5. Form factor**

Finally, we grade quantum hardware on the potential for scalability and ease of use by considering the potential for small form factors. Idealised visions of the quantum internet tend to assume that quantum devices will at some point have the footprint typically expected of laptops or even smartphones, however it is at this moment still a highly non-trivial task to realise this in practice [51]. For this reason we grade a qubit implementation on its future potential for form factor reduction.


# QUANTUM INTERNET

## An overview of Quantum Communication Architecture 
Network performance is usually evaluated on 4 major metrics:
1. Latency: time it takes for the message to travel btw user and data-center
2. Regularity: measures how the average latency is respected
3. Loss
4. Throughput or “Bandwith”: amount of data which can be sent per second

The computational costs associated with specific optimization and machine learning problems has been proved to be reduced when using Quantum Architectures.
Examples of such are:
• qPCA: a method of identification of largest eigenvalues of a matrix and it’s associated
eigenvectors
• Problems requiring polynomial time within support vector machines
Although these examples show a clear benefit in the use of Quantum machines, it is difficult to find counterparts of these examples for quantum networks.This is partly due to the age and developments in the field. Quantum Networking has made incredible progress within the last decade, but we're still far from large scale accesible testbeds, therefore making evaluations of experimental performance against classical systems is not currently possible. For this reason, we will analyse theoretical results through this sub-section.


The probabilistic nature of qubits as well their quantum properties (no cloning theorem & monogamy) have many consequences that shape quantum networking. For a start, the no cloning theorem creates a need for encoding repetition data, which is not necessary in the classic world. If a process needs 100 samples, in a quantum network we will have to perform our operation 100 times in each qubit. A higher number of operations can be associated with a higher level of energy use, but the number of repetitions done on an operation is the inverse polynomial of approximation and error parameters. At large scales, this implies a much lower need for resources within quantum networks. Lowering the number of packet requirements leads to decreased: 

- Storage needs 
- Processing within the control plane 
- Congestion 
- Source & Process delays 


Generally Energy usage is directly associated with the number of bits sent to the hypervisor (machines) & the number of instructions required for computation. These two factors are inversely related to the available bandwidth at communication links. Thus making Quantum Energy usage theoretically more efficient. 
Although those same repetitions do require softwarisation that introduces new delays & loads at other layers, the loss caused by this is theoretically offput by the benefits behing the reduction of packet requirements at large scales.

Encoding quantum information within the network is an important but expensive process. Lowering encoding cost would directly benefit the optimization of traffic and lower computational costs. We can partially do this by encoding information at a node level, but the efficiency of this technique is directly associated with the hardware properties of the channel’s ports and memories. Making the hardware used in the construction of quantum networks incredibly important for the system's efficiency and performance; a fact often overlooked in current quantum networking simulators and papers. Notably quantum memories play a crucial role in quantum information encoding, as the procerss is most efficiently performed at a local node level. This requires a strong low-loss memory, which is not an easy feat to achieve.

Additionally shared entanglement can allow for load transfer between classical and quantum channels (as long as these are defined within the same layer), making dual systems a possibility. Taking into consideration Energy efficiency when benchmarking dual protocols could significally encourage the design of efficient quantum protocols, and push for a greener Quantum Internet.
Entanglement could also reduce communication complexity, once again potentially leading to lower energy usages.


## Quantum Network requirements

The requirements depend on the user scenarios. To be considered are:
1. Connecting different types of quantum computers for distributed processing - Cross platform adaptability
2. Low loss, high efficiency, fast connections
2. Quantum Key Distribution
3. Quantum teleportation requiring a classical and quantum internet link
5. High accuracy synchronization (timeclocks, integrating telescopes)
6. Scenarios with quantum internet from home with privacy preservation - Secure and accessible connections
7. Retrieval for various types of data storage (quantum or classic data) - Dual classical/quantum architecture
8. Use of quantum internet for connecting sensors implementing quantum sensing

An IETF (Internet Engineering Task Force) Quantum Internet Research Group is IRGexploring various application scenarios base on architectural principles for a quantum internet. Sustainability is not discussed explicitly, but might be linked to the scenarios. They distinguish three application areas: quantum cryptography, sensing/metrology and quantum internet. 

Digital processing may reduce the need for physical materials, i.e. digital money reduces need for printing real money. Digital communication reduces the need for transport, digital sensing allows for coordinated monitoring of the environment. In that sense internet contributes to sustainability. The added value of quantum internet for applications is still to be demonstrated. For high quality quantum communication the quality of optical fibers is an issue. It is to be confirmed whether this will not require rare materials. Another loss of resources may be due to lack of standardization. Upgrading a fiber network infrastructure is costly. Moreover a quantum link often requires a parallel classical link like in teleportation.
If quantum computing becomes competitive with classical computing in terms of energy needs, this will also be a good argument for exploring quantum internet.

## Quantum Key Distribution

Another part of the quantum internet are quantum key distribution (QKD) systems. They can either use fiber for qubit transmission or free-space for example via satellites which has been demonstrated by China in the Micius project (2016).
They are used to generate symmetric encryption keys, but in order to generate end-to-end encryption keys over long distances, the network between the QKD devices has to be extended by quantum repeaters (or in a later development step quantum routers).
Furthermore, the development of efficient quantum repeaters is also one of the requirements to enable distributed quantum computing.
 
The development of quantum repeaters is still in its infancy, so currently no evaluation of the environmental impact can be made.
 
There also is no research on the sustainability of QKD devices available but at least for some technologies like satellite communication research on the energy efficiency [30] and for photonic integrated circuits ideas on how to develop greener devices [31] exist.
So, it is of interest to evaluate whether the properties of the devices stay the same, if the they are extended with QKD capabilities and if new materials are suitable for building QKD devices.
 
For most the QKD devices that are currently available on the market, the components used are kept secret and even system requirements are often only provided on demand. One system for which at least some system requirements are available is the IDQ Cerberis XG [32].
Power supply: “1+1 Redundant hot-swappable power supply, each 300W, 100V-240Vac, 47-63Hz, 5-2.5A”. And it offers a secret key rate of 2 kb/s on 60 km.
For Toshiba systems [33] only key rate and range are available, power consumption information is missing. 
Furthermore, there is a vast amount of different QKD technologies available: for example, there are devices that are configured in a way that they can only connect two pre-defined parties, but there are also networks where more than two users are connected using an optical switch (which does not increase the range but decreases the number of QKD devices needed). Also, multiparty QKD (more than two parties share the same key) has to be considered. Imagine a QKD device that is able to switch between P2P and multiparty mode – this might be more sustainable than having two separate devices.

It is a complex task to find a suitable measure for sustainability of QKD devices.
As a first step classes of QKD devices that can be compared meaningfully have to be defined.

As an example one could define QKD systems that connect exactly two pre-defined parties as one class. The sustainablility of these devices in operation mode could be compared by comparing the secret key rate (which might be way lower than the number of qubits exchanged depending on loss etc.) at a pre-defined distance to the power consumption of the device. But even this measurement is incomplete as it still neglects differences in the range the devices can cover.


## Simulation and integration of sustainability 
As the physical hardware is not yet available simulation is an import means to QULexplore future needs and applications. The hackathon started with the following tools for which potential extensions for sustainability are discussed:
 
- Netsquid ( https://netsquid.org/). This library allows for event simulation and design of a network infrastructure including tools to estimate the number of repeaters needed. It has been developed by QuTech and SURF. Therefore, this tools allows for estimating hardware costs. In an extension the impact on the environment could be integrated in terms of rare materials used and hardware needed for the communication lines.  
- QNE Application Development Kit (qne-adk) (https://netqasm.readthedocs.io/ ) is a library developed by QuTech. It includes an interface to simulated local quantum hardware via a universal instruction set format (NetQASM). From a sustainability point of view standardization is an issue which might be coupled with simulation. Similar to the classic simulation one might consider digital twins in which Quantum Internet.
-Quantum Network Explorer(QNE) (https://www.quantum-network.com/) gives a user friendly interface on top of Netsquid. QNE is currently being upgraded to allow experimenting with user provided scripts. The tool allows to visualise the infrastructure needed and is a helpful tool to discuss cost impact of various scenarios.
- Generic quantum computing libraries like Qiskit,Cirq. These library packages are mostly focusing on quantum computing, providing gate operations and quantum circuit composing. With connected to IBM quantum computing cloud, users are able to play with both quantum simulator and real quantum computer. Pennylane is a python library and ecosystem which includes many quantum plugs-ins (https://pennylane.ai/plugins.html) for many hardware implementations allowing for comparisons(with respect to sustainability)
- SimulaQron (Simulaqron.org). SimulaQron is an application level simulator for a quantum internet. It focuses on the quantum stack and interface with NetQASM and QNE.
- Other simulators encounteredd are QuNetSim, QuISP, Squanch,SeQUenCe, Quantum Fly (aliroquantum.com)). In general the focus is on protocols and are no references to sustainability included.


# THE SOCIAL SUSTAINABILITY OF QUANTUM

In this section, with reference to the orginal challenges:

- Can Quantum Internet be environmentally sustainable? It is concluded that metrics can be defined to help in limiting the impact.
- How can Quantum Internet contribute to Climate Justice? The burdens of climate change impacts should be distributed fairly. Quantum internet may help in given better access to computing resources. However, it is expected that it will only be implemented in densely populated regions for cost reasons. The footprints may be considered and in addition access to the applications having an impact. Note that quantum computing generate a relatively continuous thermal load.  Classical computers generate a load depending on computations. Compared to classicial internet more equipment and cooling is needed for quantum internet.


We will discuss the social aspects of sustainability.

Sustainability is a key element that must be considered in the development of new technologies. It is defined as  means meeting our own needs without
compromising the ability of future generations to meet their
own needs [40]. This requirement involves various ethical, legal and social aspects that include ecological sustainability (which has been largely discussed through this document). Nevertheless social responsibility is also an important factor within a technology's sustainability.
The Quantum community must take conciousness of the social impact of their creations, and regulate the relevant bodies accordingly. Certain goverments have already begun this action, for example in the Netherlands, a program focusing on Ethical, Legal and Social Aspects (ELSA) of quantum technologies is being initiated and the Centre for Quantum and Society (https://quantumdelta.nl/cqs/). 

As a community, we must be welcoming to all and promote diversity and accessibility. Diversity in the scientific community is necessary in order for science to have a profound impact on global society. We all need to proactively continue working to offer and implement new solutions in academia and societies for a more equal world [42]. In order to do this efficiently, we must be conscious of the current landscape of quantum. The Unitary Fund, a non-profit dedicated to helping create a quantum technology ecosystem that benefits the most people, recently ran a Quantum Open Source Software Survery which received over 1000 responses. 
Here are some of their results [26]:

- 71% users are bellow the age of 34, making the majority of contributors Gen Z.
- Half of respondents identifies as White or of European descent, 12% as South Asian, 8% as Hispanic or Latino/a/x, 6% as Black or of African descent, and 4% or below as East Asian, South East Asian, Multiracial, Middle Eastern, Other.               
- 73% of the respondents identify as male, 19% as female, 3% as non-binary, genderqueer, or gender non-conforming, 1% other and 7% prefer not to say.                     
- The largest group or respondents holds a PhD (36%) or multiple ones (2%), 33% have Masters or other non-doctoral post-graduate degree, 22% have a university degree and 8% high school/secondary school degree, other degrees, or prefer not to say                   
- The majority of quantum OSS users are researchers (55%), but almost 40% of respondents do not have a background in quantum research
- Half of respondents are affiliated to an academic institution (49%), about one third work in an enterprise organization (29%) and a quarter in a startup (25%), with 9% having no affiliation and 8% working in government
- The majority of participants are from the United States (22%), with India coming in second (12%), the United Kingdom at 9%, and Canada at 6%. EU countries sum up roughly 15%, with Germany first among them at 5%

These results give us an insight on the educational, gender and national distributions of members of the quantum open source community, but wider research must be done to have an understanding of the wider quantum community's diversity landscape.
From this survey we can infer the following:

- A very big gender gap, with 73% of respondents indentifying as male.
- A high affiliation with academia, with 49% of participants being actively affiliated to an academic body, and over 90% of participants holding a bachelors degree or higher.
- A notable interest coming from outside quantum, with 40% of participants having little to no background in quantum research.

    
Although a lot of work must be done to address the gender gap, and to welcome more non-academics into the field, the interest in Quantum outside of research is indiscutible. As a community we must foster this interest, and promote true and realistic views and news surrounding the quantum state of the art, whilst welcoming a more and more diverse group into the field.
    
# CONCLUSION

As a team, we have found many gaps in the development of a sustainable Quantum Internet. These gaps, although normal in a young developing field, must be addressed to avoid malpractices and misuses of a technology which might be key in the future of humanity. 

We propose the following lines of future work:
- **Quantum Hardware**: Researchers must be concious of the environmental and social repercusions of their research, and build quantum machines according to such a responsability. Many fields are currently disconnected from the state of the art hardware conditions, and as such could miss potential avenues for a greener more efficient quantum portfolio down the line. The use of eco friendly materials and the analysis of energy performance accross machines should be highly considered when developping quantum hardware.
- **Quantum Software**:  The integration of energy efficiency, hardware resources and other aspects relevant for understanding sustainability issues within simulators could play a key role within the community. With thousands of users of quantum software accross the globe, an accessible and available benchmarking method across simulators could greatly enhace the output of sustainability oriented research within quantum and promote eco conciousness within early researchers.

Additionally the consideration of Energy efficiency within Quantum Protocol Benchmarking, could help shape a greener more sustainable quantum internet.

**Standarization bodies** 
Research surrounding quantum sustainability and it's effects on society and the environment through it's technological lifecycle, is scarce. Promoting this avenue of research would greatly impact our understanding of the technological impact the quantum field has and may have on the world. The importance of researcher's responsibility to create and help the community arround them should not be underestimated or ignored by academic or industrial bodies. The creation of international body which supports this facet of quantum research could greatly benefit the community, by:

- Promoting and creating research groups surrounding quantum sustainability and it's effects on society and the environment through it's technological lifecycle.  (e.g. IRTF's Quantum Internet Research Group (qirg) [36] ); and adding "environmental sustainability" considerations and topics to the existing working groups and organisations, such as [37] GEANT's NETDEV-QKD "Open Quantum Group"     
- Agreeing on a definition of energy efficiency for large scale classical and quantum machines, which considers questions such as: Is the energy cost of vaccine research offput by the research's potential to save lives?
- Pushing for sustainability to be a be part of ethical, legal and social considerations when discussing quantum and society.
- Surveying the quantum community's diversity landscape and pushing for a more welcoming and diverse field.


Standarization bodies or groups which could support such an initiative include, but are not limited to: the RIPE community [38], IETF, APC, SIGCAS, SDIA, GEANT . 




REFERENCES 

1. How to measure network performance?: https://subspace.com/resources/how-to-measure-network-performance 
2.    The Computational and Latency Advantage of Quantum Communication Networks: https://arxiv.org/pdf/2106.03360.pdf 
3.    Quantum principal component analysis: https://www.nature.com/articles/nphys3029#Sec2 
4.    Quantum Support Vector Machine for Big Data Classification: https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.113.130503  
5.    X. Cao, L. Liu, Y. Cheng, and X. Shen, “Towards Energy- 
6.    Efficient Wireless Networking in the Big Data Era: A Survey,” 
7.    IEEE Communications Surveys Tutorials, vol. 20, no. 1, pp. 
8.    303–332, 2018 
9.    Protocols for Packet Quantum Network Intercommunication: https://arxiv.org/pdf/1903.10685.pdf 
10.    Rate limits in quantum networks with lossy repeaters: https://arxiv.org/pdf/2110.10168.pdf  
11.    Benchmarking of Quantum Protocols: https://arxiv.org/pdf/2111.02527.pdf   
12.    Position paper: Green Networking Metrics https://github.com/intarchboard/e-impact-workshop-public/blob/main/papers/Clemm-Dong-Mirsky-Ciavaglia-Tantsura-Odini_Green-Networking-Metrics.pdf
13.    Reducing Green House Gas Emissions With Congestion Control: https://github.com/intarchboard/e-impact-workshop-public/blob/main/papers/Welzel-Alay-Teymoori-Islam_Reducing-Green-House-Gas-Emissions-With-Congestion-Control-v2.pdf
14.   Establishing the quantum supremacy frontier with a 281 Pflop/s simulation: https://iopscience.iop.org/article/10.1088/2058-9565/ab7eeb/pdf?casa_token=fqUuMeRiHW8AAAAA:-qCFEf4B8q71vIHgiBtzWC_CMtpzILLTB5PaGoVOSn-EugRt6crwFnEY65HH3AwY_zVOkq2gmQ
15.    Is quantum computing green? An estimate for an energy-efficiency quantum advantage https://arxiv.org/pdf/2205.12092.pdf
16.    Limits of Computation https://en.wikipedia.org/wiki/Limits_of_computation
17.    Room temperature quantum key distribution characteristics of low-noise InGaAs/InP single-photon avalanche diode https://link.springer.com/article/10.1007/s40042-021-00111-4
18.    Energy Use in Quantum Data Centers: Scaling the Impact of Computer Architecture, Qubit Performance, Size, and Thermal Parameters https://ieeexplore.ieee.org/document/9827605
19.    Experimental Demonstration of Quantum Key Distribution (QKD) for Energy-Efficient Software-Defined Internet of Things https://ieeexplore.ieee.org/abstract/document/8535267
20.    Quantum supremacy using a programmable superconducting processor https://www.nature.com/articles/s41586-019-1666-5
21.    Could energy efficiency be quantum computers’ greatest strength yet? https://theconversation.com/could-energy-efficiency-be-quantum-computers-greatest-strength-yet-191989
22.    A Review of Quantum Computer Energy Efficiency https://ieeexplore.ieee.org/abstract/document/8767125
23.    Memory cost of quantum protocols https://www.researchgate.net/publication/51965796_Memory_cost_of_quantum_protocols 
24.    Universal and operational benchmarking of quantum memories https://bartoszregula.me/pdf/s41534-021-00444-9.pdf 
25.    Energy-Efficient Superconducting Computing—Power Budgets and Requirements https://ieeexplore.ieee.org/abstract/document/6449287
26.    Unitary Fund 2022 Quantum Open Source Software Survey https://unitary.fund/posts/2022_survey_results.html
27.     D. Wang, "Meeting Green Computing Challenges," 2008 10th Electronics Packaging Technology Conference, 2008, pp. 121-126, doi: 10.1109/EPTC.2008.4763421. https://ieeexplore.ieee.org/abstract/document/4763421
28.    Teuteberg, Frank, and Jorge Marx Gómez. "Green Computing & Sustainability." HMD Praxis der Wirtschaftsinformatik 47.4 (2010): 6-17. https://link.springer.com/article/10.1007/BF03340488
29.    https://www.top500.org/lists/green500/
30.    F. Alagoz and G. Gur, "Energy Efficiency and Satellite Networking: A Holistic Overview," in Proceedings of the IEEE, vol. 99, no. 11, pp. 1954-1979, Nov. 2011, doi: 10.1109/JPROC.2011.2165192. https://ieeexplore.ieee.org/abstract/document/6046158
31.    Bastos, Ana, et al. "Green photonics integrated circuits based on organic–inorganic hybrids." Nanocomposites for Photonic and Electronic Applications. Elsevier, 2020. 229-266. https://www.sciencedirect.com/science/article/pii/B9780128183960000091
32.    https://www.idquantique.com/quantum-safe-security/products/cerberis-xg-qkd-system/?gclid=EAIaIQobChMIiYDv27jY-wIVzed3Ch0cMwTZEAAYASAAEgKFHfD_BwE
33.    https://www.global.toshiba/ww/products-solutions/security-ict/qkd/products.html
34.    Pargman, Daniel, and Barath Raghavan. "Rethinking sustainability in computing: From buzzword to non-negotiable limits." Proceedings of the 8th Nordic Conference on Human-Computer Interaction: Fun, Fast, Foundational. 2014. https://dl.acm.org/doi/abs/10.1145/2639189.2639228
35.    DiVincenzo, D.P. (2000), The Physical Implementation of Quantum Computation. Fortschr. Phys., 48: 771-783. https://doi.org/10.1002/1521-3978(200009)48:9/11<771::AID-PROP771>3.0.CO;2-E
36.   IRTF's Quantum Internet Research Group (qirg) https://datatracker.ietf.org/rg/qirg/about/
37.    GEANT's NETDEV-QKD "Open Quantum Group" https://wiki.geant.org/display/NETDEV/Open+Quantum+Group+Meeting
38.    RIPE Community https://ripe.net/ripe 
39.    Huppler, K.R. (2013).  Performance Per Watt - Benchmarking Ways to Get More for Less. In: Nambiar, R., Poess, M. (eds) Selected Topics in Performance Evaluation and Benchmarking. TPCTC 2012. Lecture Notes in Computer Science, vol 7755. Springer, Berlin, Heidelberg. https://doi.org/10.1007/978-3-642-36727-4_5
40.    What is sustainability? -MCgill https://www.mcgill.ca/sustainability/files/sustainability/what-is-sustainability.pdf
41.    Haener, T., Soeken, M., Roetteler, M., Svore, K.M. (2018).  Quantum Circuits for Floating-Point Arithmetic. In: Kari, J., Ulidowski, I. (eds) Reversible Computation. RC 2018. Lecture Notes in Computer Science(), vol 11106. Springer, Cham. https://doi.org/10.1007/978-3-319-99498-7_11
42.    The Global Scientific Communit Needs to Promote Diversity https://neuronline.sfn.org/diversity/the-global-scientific-community-needs-to-promote-diversity-in-research-together
43.    Environmental IMPACT OF IT: Desktops, laptops and screens. IT Services. (2022, April 13). Retrieved December 2, 2022, from https://www.it.ox.ac.uk/article/environment-and-it 
44.    Kelemen, B., & Stonor, A. (2022, September 16). Can the west shake its dependence on China's rare earths? – The Diplomat. Retrieved December 2, 2022, from https://thediplomat.com/2022/09/can-the-west-shake-its-dependence-on-chinas-rare-earths/ 
45.    Finch, C. (2016, October 26). The toxic components of computers and monitors. Small Business - Chron.com. Retrieved December 2, 2022, from https://smallbusiness.chron.com/toxic-components-computers-monitors-69693.html 
46.    Jacobs, J. (2022, July 25). An unequal embrace of digitalization may contribute to recession risk. Brookings. Retrieved December 2, 2022, from https://www.brookings.edu/blog/techtank/2022/07/26/an-unequal-embrace-of-digitalization-may-contribute-to-recession-risk/ 
47.    PC cooling: The importance of keeping your PC cool. Intel. (n.d.). Retrieved December 2, 2022, from https://www.intel.com/content/www/us/en/gaming/resources/pc-cooling-the-importance-of-keeping-your-pc-cool.html 
48.    The need for universal standards in internet of things. Intellipaat Blog. (2020, October 15). Retrieved December 2, 2022, from https://intellipaat.com/blog/need-universal-standards-internet-things/ 
49.    The importance of standards in the evolution towards 800G ethernet and beyond. Embedded Computing Design. Retrieved December 2, 2022, from https://embeddedcomputing.com/application/networking-5g/ethernet-serial/the-importance-of-standards-in-the-evolution-towards-800g-ethernet-and-beyond 
50.    The Open Source Development Model: Overview, benefits and recommendations. (n.d.). Retrieved December 2, 2022, from http://aaaea.org/Al-muhandes/2008/February/open_src_dev_model.htm 
 52.   Wang, J.IJ., Yamoah, M.A., Li, Q. et al. Hexagonal boron nitride as a low-loss dielectric for superconducting quantum circuits and qubits. Nat. Mater. 21, 398–403 (2022). https://doi.org/10.1038/s41563-021-01187-w




THANK YOU TO THE QIH TEAM
As a team we would like to aknowledge RIPE community, the QIH organizers and our employers, for the opportunity to create this body of work.
