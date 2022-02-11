| Start Time   | End Time  | Title  | Facilitator/Speaker  | Organization  |
|:---:|:---:|:---:|:---:|:---:|
| xxx | x | xxxxxxxxx | xx | xxx |


# Observation

The computing power requirements of spacecraft computers are increasing.

Larger sensors and more complex tasks: vision navigation, self-driving operations.

Onboard GPUs can provide high performance while consuming little power.

# Objective

Evaluate GPU IP for potential future space processors, as well as COTS GPUs.

# Tasks

- Conduct a cutting-edge study on
    - existing GPUs (UE IPs and COTS)
    - existing and future spatial algorithms
- Select promising embedded GPUs (benchmark and comparison)
- Proof of concept for the space application on the best candidate: EUCLID NIR GPU.
- Create a roadmap for the use of GPUs in space.

Due to their wide availability, only CUDA/OpenCL were studied in this project.

# Lessons learned

1. A wide range of existing and future spatial algorithms can be accelerated by modern CPUs.

2. The only way to know for sure whether an algorithm is accelerated is to port it to a GPU.

3. In the absence of extensive testing, there is no easy way to select the most appropriate GPU IP from multiple vendors at a low cost.

4. In the future, similar publicly funded projects will require a significant budget for FPGA prototypes of commercial IP designs.

5. Already available open source GPU designs are ineligible for this purpose. 

6. The RISC-V and Open Hardware movements could pave the way for a commercially viable open source space GPU.

7. In terms of performance, NVIDIA GPUs outperform AMD properties, but the latter are more space-efficient.

8. Vertical integration at NVIDIA results in tighter control over product releases, both hardware and software, but the hw/sw gap remains.

9. Complex space software is in short supply.

10. To get the most out of public funding, open source benchmarks are required.

11. The board's power requirements are met by embedded GPUs.

12. OpenCL does not have the same level of programmability as CUDA and HIP.

13. The high initialization cost of vendor-optimized libraries makes them not always the best choice; however, this depends on the application scenarios

14. With a reasonable GPU development effort, high performance is achievable. Real-world implementation is the only way to assess performance.

15. When compared to other technologies, GPUs can dramatically accelerate the processing of complex spaces.

16. GPU reliability solutions developed for the automotive industry can be applied to space applications.


# Conclusion

COTS embedded GPU SoCs are powerful and well suited for new applications. For new space applications where component qualification is not critical, GPUs can offer faster time-to-market than FPGAs.
GPUs could be used in institutional missions, but this would require a significant investment.
A strong industry consortium is needed, which includes the GPU IP provider. Fault-tolerant, open-source GPU IPs with advantageous commercial licenses could be a solution.


