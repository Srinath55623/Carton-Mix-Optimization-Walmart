# Carton-Mix-Optimization-Walmart

**Introduction & Objective**

As Walmart's e-commerce business grew, dedicated Distribution Centers (DCs) were established to fulfill online orders placed through Walmart.com.
The Carrollton, Georgia DC (CDC) processes over 100,000 shipments daily during peak periods but was operating with a suboptimal carton mix — the specific set of box sizes available for packing.

**The Problem -**
Misalignment between product size and carton size leads to:

"Shipping air" — wasted space inside boxes
Higher shipping charges due to dimensional weight billing

**The Goal**:

Develop an optimized carton mix for both automated and manual packing lines to:

**Minimize the Total Order-Fulfillment Cost (TOFC)**
= Material Costs + Void-Fill Costs + Labor Costs + Shipping Costs


**Problem Description**

**The Core Trade-Off**

Too Few Box Sizes  - Wastes shipping space ("shipping air"), Higher dimensional weight charges

Too Many Box Sizes- Increases complexity, Frequent machine changeovers and Increased labor downtime

**Goal**: Find the optimal specifications for a small set of boxes that fits the widest range of products at the lowest cost.

**Model Overview**
A Mixed-Integer Optimization Model was developed involving:

**Discrete decisions** — selecting specific box sizes
**Continuous variables** — dimensions and associated costs

**Decision Variables**:

Carton Count (k): Number of active carton sizes in the system

Dimensions: Length, Width, Height for each of the k cartons

**Analysis**

**Objective Function**

**Minimize TOFC** = Material Cost + Void Fill Cost + Shipping Cost + Labor Cost


**Constraints**

Demand: LimitEvery single-unit order must fit into at least one chosen box size

Automation LimitMax 4 carton sizes (one per machine line) to eliminate changeover downtime

Manual LimitMax 6 carton sizes due to limited physical stacking space

Physical LimitsBox dimensions: 8×6×5 to 36×24×18 inches; Length ≤ 1.2 × Width


**Methodology — Custom Optimization Heuristic**

Rather than using commercial solvers (e.g., CPLEX), the team built a custom heuristic for two key reasons:

Complexity — Combinatorial nature of selecting discrete box sizes for thousands of varying products makes exact solutions computationally prohibitive

Usability — Walmart managers needed a transparent, validatable tool — not a "black box" algorithm

Adaptability — Easily reconfigurable for distinct demand cycles (Peak vs. Non-Peak seasons)

**Results & Conclusions**
 **Financial Impact**
 
Pilot Period Savings (3-week peak)- $78,336

Cost reduction — Manual cartons    14.1%

Cost reduction — Automated cartons   2%

Projected Annual Savings (Carrollton DC)   $394,700

Certified Actual Savings (Walmart Finance)    $600,000/year

Network-Wide Projected Savings       $2,000,000/year

**Key Takeaways**

**Practicality Over Perfection** — A heuristic approach ensured the tool was actually adopted and maintained by Walmart managers
**Comprehensive Cost Modeling** — Integrated shipping and void-fill costs, addressing the hidden cost of "shipping air"
**Validated Impact** — Savings certified by Walmart's internal finance team, proving real-world robustness


**Limitations**:

1)Heuristic vs. Exact OptimizationNo mathematical guarantee that the global optimal solution was found

2)ScopeCovers only single-unit orders (~75% of volume); multi-unit orders use a separate fluid-packing algorithm

3)Static NatureModel solves for static Peak/Non-Peak periods; a dynamic real-time model could yield higher savings

**Presenters**

Srinath Manda

Yash Sharma

Shravan Naikini

**Source Paper**:
Ahire, S. L., Malhotra, M. K., & Jensen, J. B. — Carton-Mix Optimization for Walmart.com Distribution Centers
ShareContentCarton-Mix Optimization for Walmart.com  Distribution Centers.pptxpptx
