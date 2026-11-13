# Playbook: navigation

Site and app navigation: header and sidebar menus, tab bars, dropdown and mega menus,
breadcrumbs, and the entry points to search.

## Laws that matter most

1. **Jakob's Law and Mental Model.** People look for navigation where other products put
   it and expect it to be named in words they know.
2. **Hick's Law and Chunking.** A long flat menu is slow to scan. Groups with labels turn
   many links into a few choices.
3. **Serial Position Effect.** The first and last items in a bar are the ones people
   remember.
4. **Fitts' Law and Accot-Zhai Steering Law.** Menu items must be easy to hit, and
   moving through a menu must not require steering along a thin path.
5. **Short-Term Memory.** People should never have to remember where they are.
6. **Discoverability.** Hiding navigation makes a tidy screen and a lost user.

## Build rules

1. **Put navigation where the platform puts it.** Header or left sidebar on desktop web.
   A bottom tab bar or the platform's standard pattern on mobile. Logo top left, linking
   home, in left-to-right layouts.
2. **Name things in the user's words.** Labels describe what people will find, not how
   the company is organized. One name per destination, used everywhere.
3. **Group long menus.** When the top level grows past what can be scanned at a glance,
   group related destinations under a few labeled headings. Do not cut needed
   destinations to hit a number: "seven plus or minus two" is not a rule for menus
   (Miller's Law). As a working heuristic, more than five to seven ungrouped top-level
   items is a prompt to group.
4. **Order with intent.** If a conventional or logical order exists (Home first, account
   last, alphabetical for long lists), use it. Otherwise put the most used destinations
   at the start and end of the bar and the least used in the middle.
5. **Keep primary navigation visible on wide screens.** Do not hide it behind a hamburger
   or "More" menu where there is room to show it. On small screens show the top few
   destinations and put the rest one tap away, with text labels.
6. **Label icons.** A tab bar or icon rail has a text label under or beside each icon.
7. **Show where the person is.** The current section is marked in the navigation by more
   than color. Deep pages have breadcrumbs or a visible parent. Page titles match the
   link that led to them.
8. **Make items easy to hit.** Each item is a full-size target: the whole row or tab is
   clickable, not only the text. Meet the platform minimum (44 by 44 pt on Apple
   platforms, 48 by 48 dp on Android, at least 24 by 24 CSS px on the web).
9. **Limit depth.** No more than two levels in a dropdown or flyout. Deeper structure
   belongs on a page, in a mega menu with visible groups, or in search.
10. **Open menus on click or tap.** If a menu opens on hover, add a short delay, keep it
    open while the pointer moves diagonally toward it, and make sure it also opens on
    click, focus and touch.
11. **Use real links** so people can open in a new tab, copy the address and go back.
    The back button must work.
12. **Offer search** when there are more destinations or items than a menu can hold, in
    the place people expect it, and run it on Enter.
13. **Keep navigation stable.** Same items, same order, same place on every page.

## Checks

| Check | Law |
|---|---|
| Is the navigation in the platform's conventional place, with the logo linking home? | Jakob's Law |
| Count the top-level items. If there are many, are they grouped under labels? | Hick's Law, Chunking |
| Would a new user recognize every label? Any internal or branded terms? | Mental Model, Conceptual Model |
| Are the most used destinations first or last in the bar, unless convention fixes the order? | Serial Position Effect |
| Is primary navigation visible without opening a menu on wide screens? | Discoverability |
| Does every icon have a text label? | Signifiers |
| Is the current location marked, by more than color? | Short-Term Memory, Feedback |
| Is each item's whole row or tab clickable and at least the platform minimum size? | Fitts' Law |
| Are flyout menus two levels deep at most? | Accot-Zhai Steering Law |
| Do hover menus tolerate diagonal movement and also open on click and focus? | Accot-Zhai Steering Law |
| Are items real links, and does the back button work? | Jakob's Law |
| Is the navigation identical across pages? | Law of Similarity |
| On a phone width, can the main destinations be reached in one tap? | Fitts' Law, Principle of Least Effort |

## Mistakes this screen invites

The flat mega-nav, the mystery icons, the cascade maze, the hover secret, the tiny
target, the reinvented control (custom scroll or back behavior), color-only signal (for
the current page).

## When laws conflict here

- **Fewer items against findability.** Group, do not hide. Frequent destinations stay
  visible (Discoverability over Hick's Law). Rare ones go in one labeled place.
- **Key items at the ends against conventional order.** Convention wins. Use emphasis for
  the key item instead (Jakob's Law over Serial Position Effect).
- **Compact menus against easy targets.** On touch, size wins. On desktop, compact rows
  are acceptable down to the WCAG 2.2 AA minimum.
- **Clean header against visible navigation.** Visible wins on wide screens.

## Research that settles what the laws cannot

How users group your content and what they call each group: a card sort. Whether they can
find things in the proposed structure: a usability test with find-it tasks. The
`../methods/card-sorting.md` and `../methods/usability-test.md` have both.
