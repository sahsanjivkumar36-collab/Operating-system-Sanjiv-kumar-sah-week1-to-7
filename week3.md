Week 3 — Application Selection & Performance Workload Planning
Home | Week 2 | Week 3 | Week 4 →
________________________________________
Overview
Week 3 focuses on selecting representative applications and services to evaluate the performance behaviour of the Linux operating system under different workload conditions. Each application is chosen to stress a specific system resource, allowing structured and measurable analysis of CPU, memory, disk, and network performance in later testing phases.
This phase links operating system theory to practical evaluation by predicting expected resource usage and defining monitoring strategies before execution.
________________________________________
Objectives
•	Select applications representing different workload types
•	Justify application choices based on system resource impact
•	Document installation procedures using SSH-based commands
•	Define expected resource usage profiles
•	Plan monitoring strategies for each workload
________________________________________
Deliverables
•	Application selection matrix
•	Installation documentation with exact commands
•	Expected resource usage profiles
•	Monitoring strategy for each selected application
________________________________________
1. Application Selection Strategy
To comprehensively evaluate operating system behaviour, applications were selected to represent diverse workload categories commonly encountered in real-world server environments. This approach enables targeted performance analysis and identification of system bottlenecks.
The selected workload types include:
•	CPU-intensive workloads
•	Memory-intensive workloads
•	Disk I/O–intensive workloads
•	Network-intensive workloads
•	Server-based services
________________________________________
2. Application Selection Matrix
Workload Type	Application	Purpose	Justification
CPU-intensive	stress-ng	CPU load generation	Designed to stress CPU scheduling and processing
Memory-intensive	stress-ng	Memory allocation testing	Evaluates memory management and swapping behaviour
Disk I/O–intensive	fio	Disk read/write benchmarking	Measures filesystem and disk I/O performance
Network-intensive	iperf3	Network throughput testing	Evaluates bandwidth and latency
Server application	Apache HTTP Server	Service workload simulation	Represents a real-world server process
This combination provides balanced coverage of core operating system subsystems.
________________________________________
3. Installation Documentation
All software installations will be performed remotely via SSH from the workstation, in accordance with coursework constraints.
3.1 Package Update
sudo apt update
sudo apt upgrade -y
________________________________________
3.2 Application Installation Commands
stress-ng
sudo apt install stress-ng -y
fio
sudo apt install fio -y
iperf3
sudo apt install iperf3 -y
Apache HTTP Server
sudo apt install apache2 -y
Each installation command will be executed via SSH and documented with screenshots showing the command prompt and successful installation output.
________________________________________
4. Expected Resource Usage Profiles
4.1 CPU-Intensive Workloads (stress-ng)
•	High CPU utilisation across multiple cores
•	Increased system load averages
•	Potential thermal throttling under sustained load
________________________________________
4.2 Memory-Intensive Workloads (stress-ng)
•	Rapid memory allocation
•	Increased RAM usage and potential swap utilisation
•	Impact on system responsiveness
________________________________________
4.3 Disk I/O–Intensive Workloads (fio)
•	Sustained read/write operations
•	Increased disk latency under load
•	Potential bottlenecks depending on filesystem configuration
________________________________________
4.4 Network-Intensive Workloads (iperf3)
•	High network throughput
•	Measurement of bandwidth and latency
•	Impact of network stack configuration
________________________________________
4.5 Server Application Workloads (Apache)
•	Moderate CPU and memory usage
•	Network-driven request handling
•	Service response time under load
________________________________________
5. Monitoring Strategy
Monitoring will be performed remotely from the workstation using SSH-based tools to avoid interference with server performance.
5.1 Monitoring Tools
•	top / htop – CPU and process monitoring
•	free -h – Memory usage analysis
•	df -h and iostat – Disk utilisation and I/O performance
•	ss, ip, ping – Network monitoring and latency
•	systemctl status – Service health checks
________________________________________
5.2 Measurement Approach
•	Baseline measurements recorded before workload execution
•	Load testing conducted with one workload at a time
•	Metrics captured at regular intervals
•	Results stored in structured tables for analysis
This approach ensures repeatability and reliable comparison between workloads.
________________________________________
6. Preparation for Performance Testing
The applications and monitoring strategies defined in this phase will be used during Week 6 to conduct detailed performance evaluation. Expected resource profiles provide a benchmark against which actual results can be compared, enabling identification of inefficiencies and optimisation opportunities.
________________________________________
Reflection
Key Design Decisions
•	Selection of lightweight but representative benchmarking tools
•	Use of both synthetic and real-world server workloads
•	SSH-based monitoring to maintain realistic administration conditions
Anticipated Challenges
•	Avoiding overlapping resource contention during testing
•	Interpreting performance data accurately
•	Balancing workload intensity with system stability
Learning Objectives Achieved
•	Understanding how applications stress different OS subsystems
•	Ability to plan performance evaluation using appropriate tools
•	Linking theoretical OS concepts to practical measurement
________________________________________
References
stress-ng Documentation
https://wiki.ubuntu.com/Kernel/Reference/stress-ng
fio Documentation
https://fio.readthedocs.io
iperf3 Documentation
https://iperf.fr
Apache HTTP Server Documentation
https://httpd.apache.org/docs/

