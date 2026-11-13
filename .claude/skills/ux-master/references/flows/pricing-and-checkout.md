# Playbook: pricing and checkout

Pricing pages, plan pickers, carts, checkout and payment. For the form fields themselves
also read `forms.md`. For loading, error and confirmation states also read `states.md`.

## Laws that matter most

1. **Hick's Law and Analysis Paralysis.** Choosing a plan is the hardest decision on the
   page. The more options and the harder they are to compare, the more people postpone.
2. **Von Restorff Effect.** One recommended option, clearly different, gives people a
   place to start.
3. **Cognitive Bias.** Pricing is where interfaces most often steer people against their
   interest. Total cost, add-ons and urgency must be honest.
4. **Jakob's Law.** People know how carts and checkouts work. Follow the pattern.
5. **Parkinson's Law and Postel's Law.** Paying should be quick, and the form should
   accept what people type.
6. **Goal-Gradient Effect and Peak-End Rule.** Show how close people are to done, and
   end with a confirmation worth remembering.

## Build rules: pricing

1. **Show few plans at once.** Lead with the plans most visitors choose between and put
   the rest behind a labeled link such as "Compare all plans". There is no published
   maximum. As a working heuristic, three or four in view is a common, comparable set.
2. **Recommend exactly one.** Mark it with a text label and at least one more cue that is
   not color: size, a filled button, position. It should be the plan that fits most
   visitors, not only the most expensive.
3. **Make plans comparable.** List the same attributes in the same order on every plan.
   Lead with what differs. Put the full matrix in a comparison table below.
4. **Keep each plan in one region.** Name, price, what is included and the button sit
   inside the same card (Law of Common Region).
5. **State the real price.** Show the billing period, per-seat terms, minimums and any
   required fees next to the price, in readable text. Nothing that changes the total
   lives only in a tooltip, a hover or the fine print.
6. **Make the billing toggle honest and obvious.** Both prices update when it changes.
   The selected state is clear without relying on color. The saving is shown as a real
   figure.
7. **Name each button for what it does.** "Start free trial", "Choose Team", "Contact
   sales". A plan that needs a sales conversation does not get a self-serve button.
8. **No manufactured urgency.** No countdown or scarcity message unless it is backed by a
   real deadline or real stock.

## Build rules: cart and checkout

9. **Use the familiar order.** Cart, details, payment, review, confirmation. Keep the
   cart reachable from every page.
10. **Show the order all the way through.** Items, quantities, discounts and the running
    total stay visible on every step (Short-Term Memory).
11. **Show the full total early.** Tax, shipping and fees appear as soon as they can be
    calculated, not first on the last step.
12. **Offer guest checkout** where the business allows. Offer account creation after the
    purchase.
13. **Add-ons are unchecked by default** and described with their price. Declining is as
    easy as accepting.
14. **Shorten the work.** Autofill, saved details, "billing same as shipping" checked by
    default, express payment options, card type detected from the number.
15. **Show progress** across steps with named steps and the current position.
16. **Protect the pay action.** One primary button that states the action and the amount
    ("Pay $48.00"). Acknowledge the press within 400 ms, disable the button and show that
    payment is in progress. Do not allow a double charge.
17. **Fail well.** If payment fails, keep every field, say what failed and what to try,
    and offer another payment method.
18. **End properly.** Confirm what was bought, the amount, a reference number, what
    happens next and when, and where to get help. Send the same by email.
19. **Make cancel and downgrade as easy as subscribe.**

## Checks

| Check | Law |
|---|---|
| Count the plans in view. Is one recommended, by more than color? | Hick's Law, Von Restorff Effect |
| Do all plans list the same attributes in the same order? | Analysis Paralysis |
| Is each plan's button inside that plan's region? | Law of Common Region |
| Are period, seats, minimums and fees stated beside the price in readable text? | Cognitive Bias, Discoverability |
| Does the billing toggle change the prices and show its state clearly? | Feedback, Stroop Effect |
| Is any urgency or scarcity message backed by real data? | Cognitive Bias |
| Are add-ons unchecked by default? | Cognitive Bias |
| Is the order summary visible on every checkout step? | Short-Term Memory |
| Is the full total shown before the final step? | Cognitive Bias |
| Does the checkout follow the conventional order, with a guest path? | Jakob's Law, Principle of Least Effort |
| Are `autocomplete` values set on address and card fields, and do card and phone fields accept spaces? | Parkinson's Law, Postel's Law |
| Is there a step indicator? | Goal-Gradient Effect |
| Does the pay button state the amount, respond at once and prevent a second press? | Feedback, Doherty Threshold |
| Does a failed payment keep the input and offer a way forward? | Peak-End Rule, Feedback |
| Does the confirmation state what was bought, the reference and what happens next? | Peak-End Rule |
| Are buttons large enough to hit on a phone (44 pt on Apple platforms, 48 dp on Android, at least 24 CSS px on the web)? | Fitts' Law |

## Mistakes this screen invites

The equal-cards grid, the feature wall, everything is primary, the dark nudge, the hover
secret (terms shown only on hover), the silent button (on Pay), the memory test (order
details not carried forward), the dead end (a bare "Success").

## When laws conflict here

- **Fewer plans against the full range.** Keep every plan the business sells. Show the
  common few and make the rest one clear click away (Hick's Law with Tesler's Law).
- **Emphasis against honesty.** Recommending a plan is fine. Recommending the one that is
  worse for most visitors is not (Von Restorff Effect under Cognitive Bias).
- **Speed against safety at payment.** Payment is costly to get wrong, so a review of the
  total before paying is worth its step. Do not add confirmations elsewhere.
- **Conversion metrics against the customer.** If a tactic raises conversions by hiding
  cost or adding pressure, it will show up later as refunds and cancellations
  (Campbell's Law).

## Research that settles what the laws cannot

Which plan to recommend and which attributes matter: sales and usage data, plus
interviews with recent buyers. Whether people understand the total: a usability test in
which people say what they expect to pay before the final step.
