# Director of Operations Take-Home Assessment

**Ana Ramos**

## Executive Summary

My main takeaway from the interviews is that DI does not need a lot more process. It needs enough operational infrastructure to scale without asking its technical leaders to absorb the complexity themselves.

Today, many of the team's operating mechanisms rely on individuals: David is pulled into decisions that should not require him; Priya and Marcus coordinate dependencies through Slack and informal conversations; Finance and Compliance often learn about decisions after they have already been made; and hiring, onboarding and vendor management require significant manual coordination. These approaches can work at a team of 10, but they will become increasingly difficult as DI grows toward 30 people.

My goal would be to build what David described as **"invisible operations"**: simple, lightweight systems that make it easier for the team to move quickly, while putting the coordination, controls and visibility behind the scenes.

One principle guides the recommendations below: **structure should increase with commitment, risk and scale.** Experimentation should remain easy; meaningful commitments should become visible; and repeatable work should eventually be standardized and automated.

**Prototype:** [DI Vendor Hub](https://di-vendor-hub.lovable.app/)  
**Prototype Source Code:** [GitHub](https://github.com/anafsramos/di-vendor-hub)

---

# 1. Operational Gap Assessment

Across the interviews, I heard different versions of the same problem: **too much of DI's operating model is reactive.**

David is reacting to decisions that reach him because ownership is unclear. Priya is reacting to vendor, compliance and data dependencies after work has started. Marcus is reacting to portfolio requests without a clear view of capacity. Finance is reacting to spend after it occurs. Compliance is reacting to risk close to deployment. HR is reacting to hiring needs once they are already urgent.

I would prioritize four gaps:

### 1. Hiring and onboarding

**What I heard:** DI expects to grow from approximately 10 to 30 people over the next 18 months, but workforce planning and hiring remain largely reactive. The most recent hire took approximately three weeks to receive necessary system access, while interview scheduling and debriefs can add weeks to the recruiting process.

**Why it matters:** DI's ability to execute its roadmap depends on bringing in the right people quickly and making them productive. At 3x the team size, today's approach will become a capacity constraint and a candidate-experience risk.

**What I would change:** Create a lightweight workforce plan, standardize the recruiting loop, establish clear ownership of the candidate journey, and make Day 1 access and DI-specific onboarding predictable.

### 2. Vendor, procurement and compliance workflow

**What I heard:** Vendor management is fragmented across the requester, David, Finance, Compliance and Legal. Priya described spending roughly 20 hours over three weeks coordinating one vendor process. Finance sometimes discovers subscriptions after an invoice arrives, while Compliance can first learn about data or AI risks near launch.

**Why it matters:** This creates both unnecessary friction and unnecessary risk. A $100 low-risk tool should not require the same process as a six-figure, multi-year data agreement.

**What I would change:** Create one lightweight intake that routes requests according to cost, commitment and risk. Operations should own the system, not every transaction that runs through it.

### 3. Demand, prioritization and capacity

**What I heard:** Both pods described strong working relationships but limited shared visibility. Portfolio-company requests can arrive informally and become commitments before capacity and dependencies are fully understood. David then gets pulled in when priorities collide.

**Why it matters:** As DI grows, the cost of saying yes without understanding capacity will grow with it. DI also risks prioritizing the loudest or most urgent request rather than making explicit tradeoffs.

**What I would change:** Introduce a lightweight view of active initiatives, upcoming demand, capacity and major dependencies. The goal is not project-management bureaucracy; it is to make tradeoffs visible before commitments are made.

### 4. Financial visibility and value measurement

**What I heard:** Finance knows DI's total spend but has limited ability to connect it to individual initiatives or outcomes. Cloud costs are already material and can change quickly. At the same time, DI's impact is often demonstrated through anecdotes rather than a consistent measurement approach.

**Why it matters:** As the team and budget grow, leadership will need better information to make resource decisions. That does not mean forcing every experiment into an ROI calculation or creating reporting for reporting's sake.

**What I would change:** Establish a basic budget and forecast cadence and improve how DI tracks impact, moving where possible from usage to workflow improvement to business or investment outcomes, and ultimately to financial impact where it can reasonably be measured.

---

# 2. 90-Day Operational Plan

I would treat the first 90 days as building the **minimum viable operating foundation**, starting with the two areas David identified as most urgent: hiring/onboarding and vendor/compliance. I would introduce the other mechanisms as lightweight pilots and add structure only where it proves useful.

| Period | Focus | What I would do |
|---|---|---|
| **Days 0–30** | **Fix immediate friction + learn** | Establish a workforce/hiring view; standardize recruiting and onboarding basics; launch a simple vendor/compliance intake; inventory current vendors and upcoming renewals; baseline spend and current initiatives |
| **Days 31–60** | **Improve visibility + coordination** | Refine vendor routing based on usage; introduce a lightweight cross-pod capacity/prioritization view; establish a Finance forecast cadence; pilot a more structured intake for portfolio requests |
| **Days 61–90** | **Make what works repeatable** | Automate repeatable steps; remove mechanisms that are not useful; establish quarterly workforce/capacity planning; define the next operational priorities based on what the first 60 days revealed |

I would expect to adjust this plan as I learn. In particular, I would resist designing DI's future organization too early. For example, Priya and Marcus both described duplicated data-engineering work, but I would first understand how frequent and costly those overlaps are before deciding that DI needs a centralized Data Engineering function.

Once the internal operating foundation is working, I would expect the role to expand toward how DI works across Deerfield and, eventually, how DI presents itself externally.

---

# 3. Cross-Functional Coordination Model

Since DI sits inside a much larger institution, I see Operations as the layer that helps DI move quickly while making it easy to engage Deerfield's existing HR, Finance, Compliance and Legal infrastructure.

**The goal is to give each function the visibility it needs without turning every interaction into an approval step.**

| Partner | DI Operations | Functional partner |
|---|---|---|
| **HR** | Workforce planning, hiring process, candidate experience and onboarding coordination | HR policy, compensation frameworks and employee-relations expertise |
| **Finance** | DI budget/forecast visibility, vendor inventory and renewals | Financial controls, accounting and firmwide policies |
| **Compliance / Legal** | Early routing, required information and process/status visibility | Compliance and legal judgment and approvals where required |
| **Technical leaders** | Capacity/dependency visibility and operating mechanisms | Technical architecture, technical standards and technical hiring decisions |
| **David** | Ops brings the information and escalates when needed | Strategy, major resource allocation and high-judgment decisions |

I would try to make this model increasingly **trigger-based rather than meeting-based**. Compliance should not need to attend every project review; it should be brought in early when a project has the characteristics that require its involvement. Finance should not approve every small software subscription; it should have visibility and become involved when spend or commitment crosses agreed thresholds.

The goal is for the controls to exist without making the team feel the controls.

---

# 4. Prototype: DI Vendor Hub

I chose vendor management for the prototype because it was one of the clearest problems raised across multiple interviews. David described spending significant time on vendor decisions; Priya spent roughly 20 hours coordinating one vendor through internal teams; Finance described discovering spend and renewals after the fact; and Compliance described being brought in too late.

I built **DI Vendor Hub** as a simple example of what "invisible operations" could look like. Someone submits a vendor request once, the tool brings in the right teams based on the request, and the status stays visible through approval and renewal.

For the prototype, I used illustrative rules: low-cost/low-risk requests can be automatically approved, while higher spend, sensitive data, external AI, longer contractual commitments or portfolio-company deployment bring in the relevant teams. The exact thresholds and rules would, of course, need to be agreed with Finance, Compliance and Legal.

**[Open DI Vendor Hub](https://di-vendor-hub.lovable.app/)**  
**[View source code](https://github.com/anafsramos/di-vendor-hub)**

This is a workflow prototype rather than a production application. It currently uses local/sample data and does not include shared storage, role-based access or integrations with Deerfield systems. A production version would require the appropriate engineering and security review, but the prototype is meant to show the operating logic and user experience.

---

# Assumptions

- I would validate the interview findings against existing systems and data before making major changes.
- DI should use Deerfield's existing infrastructure where it works rather than automatically creating DI-specific systems.
- The thresholds and routing rules in the prototype are illustrative, not proposed Deerfield policy.
- I would not redesign DI's organizational structure based on these interviews alone. I would use the first few months to understand where shared capabilities are actually needed.
- The objective is not maximum standardization. I would add structure as work becomes more costly, risky, repeatable or difficult to reverse.

---

## A final note

I would expect to **build, not only coordinate**.

I am not an engineer, but the bar for building useful internal tools has changed dramatically with AI. I would invest in becoming increasingly technical and use AI-assisted tools to prototype solutions myself before asking DI's engineers for capacity.

The DI Vendor Hub included with this submission is my first example of that approach.
