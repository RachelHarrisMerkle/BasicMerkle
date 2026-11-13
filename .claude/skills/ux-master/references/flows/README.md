
# UX flows

Six playbooks. Each one is a short brief for a kind of screen: which laws matter most
there, the rules to build to, the checks to run and the mistakes that screen invites.

## Pick the playbook

| Screen | File |
|---|---|
| Any form: sign-up, log-in, contact, settings, data entry | [forms.md](forms.md) |
| First run, setup, product tours, activation | [onboarding.md](onboarding.md) |
| Pricing pages, plan pickers, carts, checkout, payment | [pricing-and-checkout.md](pricing-and-checkout.md) |
| Site or app navigation, menus, tabs, search entry points | [navigation.md](navigation.md) |
| Dashboards, reports, lists and data tables | [dashboards-and-tables.md](dashboards-and-tables.md) |
| Empty, loading, error and success states | [states.md](states.md) |

Most screens need more than one. A checkout is a form, a payment step and several states,
so read `forms.md`, `pricing-and-checkout.md` and `states.md`. Read only the ones the
screen needs.

## How to use a playbook

**When building.** Read the playbook before you write code. Take its "Build rules" as the
constraints for the screen. Write the UX read (see `../modes/build.md`)
using the playbook's laws and name the playbook's mistakes as the defaults you will not
ship. After the build, run the playbook's checks against what you wrote.

**When reviewing.** Run the playbook's "Checks" against the screen. Each check names its
law. Report failures in the audit report shape (`../modes/audit.md`): one row per problem with law, severity,
evidence, the cost to the user and the fix. The playbook narrows where to look. It does
not replace the full audit when one is asked for.

**When the brief disagrees.** The user's content and brand decisions stand. If a
requirement breaks a rule here (a long form that legally needs every field, a plan list
that must show every tier), keep the requirement and apply the rule to its structure:
group it, order it, set defaults, recommend one.

## What every playbook assumes

- Numbers with a named source are published figures. Any other number is a working
  heuristic and is labeled as one.
- Every screen needs its states. `states.md` applies to all of them.
- When two rules pull against each other, each playbook has a "When laws conflict here"
  section. The full table is in
  `../laws/which-law-wins.md`.
- A playbook cannot tell you what your users know or want. When a decision depends on
  that, it says which research method to use. `../modes/research.md` runs them.
