flowchart TD
    subgraph A [Phase 1: User Access & Provisioning]
        direction LR
        A1[Users<br>Trainees & Instructors] --> A2[Web Portal<br>React.js UI]
        A2 -- Authenticate via --> A3[Azure Active Directory<br>RBAC]
        A3 -- Grants Access --> A2
        A2 -- Triggers --> A4[API Server<br>Node.js + Express]
        A4 -- Executes --> A5[Infrastructure as Code<br>ARM Templates]
        A5 -- Deploys --> B
    end

    subgraph B [Phase 2: Core Training Environment]
        B1[Isolated Azure Virtual Network<br>VNet]
        
        subgraph B2 [Red Team Resources]
            R1[Kali Linux VM<br>Attack Tools]
            R2[Command & Control<br>C2 Server]
        end

        subgraph B3 [Blue Team Resources]
            B4[Windows Server VMs<br>Applications & Data]
            B5[SIEM & SOC Tools<br>Azure Sentinel]
        end

        B1 --> B2
        B1 --> B3
    end

    A -- Provisions --> B

    subgraph C [Phase 3: Real-Time Monitoring & Analysis]
        direction LR
        B2 -- 
