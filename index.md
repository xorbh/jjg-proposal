---
layout: default
title: AI Transformation Engagement
---

We're excited about the opportunity to partner with JJG Manufacturing on integrating AI across your operations. The engagement is structured as a series of projects, each building on the last — starting with understanding where you are today and progressively introducing automation and AI where it can make the biggest difference.

All work is billed on a **time-and-materials basis**. The projects below represent the likely shape of the engagement; exact scope and sequencing will be refined together as we learn more about your operations.

---

<style>
  .proj-timeline { display: flex; flex-direction: column; gap: 10px; margin-top: 1.5rem; }
  .proj-row { border: 1px solid #e0e0e0; border-radius: 8px; overflow: hidden; transition: box-shadow .15s; background: #fff; }
  .proj-row:hover { box-shadow: 0 0 0 1.5px #bbb; }
  .proj-header { display: flex; align-items: center; justify-content: space-between; gap: 12px; padding: 14px 16px; cursor: pointer; user-select: none; }
  .proj-label { font-size: 15px; font-weight: 600; color: #1a1a2e; }
  .proj-theme { font-size: 13px; color: #666; margin-top: 2px; }
  .chevron { font-size: 11px; color: #999; transition: transform .2s; flex-shrink: 0; }
  .proj-row.open .chevron { transform: rotate(180deg); }
  .proj-details { display: none; border-top: 1px solid #eee; padding: 16px; }
  .proj-row.open .proj-details { display: block; }
  .details-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; }
  .detail-block h4 { font-size: 11px; font-weight: 600; color: #888; text-transform: uppercase; letter-spacing: .05em; margin-bottom: 8px; }
  .detail-list { display: flex; flex-direction: column; gap: 6px; }
  .detail-item { display: flex; align-items: flex-start; gap: 8px; font-size: 14px; color: #333; line-height: 1.45; }
  @media (max-width: 540px) { .details-grid { grid-template-columns: 1fr; } }
</style>

<div class="proj-timeline" id="timeline"></div>

<script>
const projects = [
  {
    label: "Project 1",
    theme: "Discovery & opportunity mapping",
    advisory: [
      "Walk the floor — understand how things actually work across production, quality, maintenance, and planning",
      "Review existing systems, data sources, and manual processes to identify where AI and automation could add value",
      "Assess data readiness — what's available, what's reliable, and where the gaps are",
      "Deliver a prioritised opportunity map that guides everything that follows",
    ],
    outcomes: [
      "Shared understanding of where the highest-impact opportunities are",
      "Clarity on data and system readiness for each opportunity",
      "Agreed priorities and sequencing for subsequent projects",
    ]
  },
  {
    label: "Project 2",
    theme: "Production visibility & intelligence",
    advisory: [
      "Explore how production data could be surfaced more effectively — yield, scrap, cycle times, operator performance",
      "Identify opportunities for AI-driven insights such as anomaly detection, trend analysis, or predictive alerts",
      "Evaluate what can be built with existing data versus what would require new instrumentation",
    ],
    outcomes: [
      "Better visibility into what's happening on the shop floor in near real-time",
      "Early identification of production issues before they compound",
      "Foundation for more advanced AI applications downstream",
    ]
  },
  {
    label: "Project 3",
    theme: "Quality & scrap reduction",
    advisory: [
      "Investigate patterns in scrap and rework data — where losses are concentrated and what drives them",
      "Explore whether predictive models could flag at-risk batches or processes before defects occur",
      "Consider how quality data could be fed back into planning and operator guidance",
    ],
    outcomes: [
      "Deeper understanding of root causes behind scrap and quality issues",
      "Potential for meaningful reduction in material waste and rework costs",
      "Tighter feedback loop between quality outcomes and production decisions",
    ]
  },
  {
    label: "Project 4",
    theme: "Maintenance & machine uptime",
    advisory: [
      "Review current maintenance practices — how issues are logged, how preventive schedules are managed, where breakdowns cause the most disruption",
      "Assess whether machine and sensor data could support condition-based or predictive maintenance approaches",
      "Explore ways to reduce unplanned downtime through smarter scheduling and alerting",
    ],
    outcomes: [
      "More proactive approach to maintenance, less firefighting",
      "Potential reduction in unplanned downtime and associated production losses",
      "Better allocation of maintenance resources based on actual machine condition",
    ]
  },
  {
    label: "Project 5",
    theme: "Planning & delivery performance",
    advisory: [
      "Look at how production planning, scheduling, and delivery commitments could be better informed by real-time data",
      "Explore AI-assisted forecasting and scheduling to improve on-time delivery",
      "Identify bottlenecks and capacity constraints that are difficult to see with current tools",
    ],
    outcomes: [
      "More realistic and adaptive production schedules",
      "Improved on-time delivery performance and customer confidence",
      "Better forward visibility for leadership on capacity and commitments",
    ]
  },
  {
    label: "Project 6",
    theme: "Operational AI assistant & knowledge capture",
    advisory: [
      "Explore how an AI assistant could help teams access information, answer operational questions, and surface relevant data across systems",
      "Consider how institutional knowledge — tribal knowledge, SOPs, historical decisions — could be captured and made accessible",
      "Define what ongoing support and evolution looks like beyond the initial engagement",
    ],
    outcomes: [
      "Faster access to the right information for people across the organisation",
      "Reduced dependency on key individuals for operational knowledge",
      "Clear view of ROI from the engagement and a roadmap for what comes next",
    ]
  }
];

function render() {
  const tl = document.getElementById('timeline');
  projects.forEach((p, i) => {
    const div = document.createElement('div');
    div.className = 'proj-row';
    div.id = 'row-' + i;
    div.innerHTML = `
      <div class="proj-header" onclick="toggle(${i})">
        <div>
          <div class="proj-label">${p.label}</div>
          <div class="proj-theme">${p.theme}</div>
        </div>
        <div class="chevron">▼</div>
      </div>
      <div class="proj-details">
        <div class="details-grid">
          <div class="detail-block">
            <h4>What we'd explore</h4>
            <div class="detail-list">
              ${p.advisory.map(a => `
                <div class="detail-item">
                  <span style="color:#999;margin-top:3px;font-size:12px">—</span>
                  <span>${a}</span>
                </div>
              `).join('')}
            </div>
          </div>
          <div class="detail-block">
            <h4>Potential outcomes</h4>
            <div class="detail-list">
              ${p.outcomes.map(o => `
                <div class="detail-item">
                  <span style="color:#2563eb;font-size:14px;margin-top:1px">&#10003;</span>
                  <span>${o}</span>
                </div>
              `).join('')}
            </div>
          </div>
        </div>
      </div>
    `;
    tl.appendChild(div);
  });
}

function toggle(i) {
  document.getElementById('row-' + i).classList.toggle('open');
}

render();
document.getElementById('row-0').classList.add('open');
</script>

---

## How We Work

All work is billed on a **time-and-materials basis** at pre-agreed rates. This keeps things flexible — scope can shift as we learn, and you only pay for the work that gets done.

- Projects are tackled sequentially, though there may be natural overlap
- Each project begins with a brief scoping conversation to align on goals and expected effort
- Regular check-ins keep you informed without creating overhead
- No long-term lock-in — either party can pause or wrap up with 30 days' notice

### What's Not Included

- Third-party platform, infrastructure, or licensing costs (billed separately at cost)
- Travel expenses (billed at cost)

---

## Next Steps

We'd welcome your thoughts on whether this structure feels right for how JJG operates. A few things that would help us get started:

1. Are there areas you'd want to prioritise — or any you'd want to defer?
2. Who would be the key contacts on the JJG side for the discovery phase?
3. What does your preferred timeline look like for kicking things off?

We're happy to walk through any of this in more detail.
