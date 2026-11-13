# Conceptual Model

Interaction Principle card. Audit lens: Expectations.

Related cards in the deck: [Discoverability](discoverability.md), [User Interview](user-interview.md).

## In one line

A conceptual model is the simplified explanation of how something works that a person builds from using it, being shown it and being told about it.

## What it asks of an interface

- People do not need the real mechanism. They need a story that predicts what will happen when they act, and what to do when something goes wrong.
- Good models borrow from things people already know: files and folders, a cart, a trash can, an inbox.
- The interface is the main source of the model. Names, structure and feedback all teach it, whether you intend them to or not.
- When the model people form does not match how the system behaves, they act wrongly with confidence and get frustrated.

## When it applies

- Naming of objects and actions, navigation structure, onboarding, sync and sharing, anything with saved state or permissions.
- New kinds of product, where no existing model can be borrowed whole.

## Detect a violation

**In code**

- One concept with several names across the product (Project, Workspace, Board used for the same thing), or one name used for two different things. Search the user-facing strings.
- Internal or technical terms in the interface: IDs, table names, enum values, status codes shown as labels.
- Metaphors used inconsistently: a "trash" that deletes immediately, an "archive" that cannot be reopened, a "draft" that other people can already see.
- Actions whose scope is unclear from the label: "Delete" (this item, or everything selected, or the whole account?), "Share" (with whom?), "Sync" (which direction?).
- State that is saved automatically in some places and needs an explicit save in others, with no cue telling them apart.

**In a screenshot or design file**

- Read only the navigation labels and headings. Can you describe what the product is and what its main objects are?
- Two screens that show the same kind of object with different names or different layouts.
- Icons or metaphors that promise behavior the product does not have.

## Example

**Bad:** An app that calls the same thing a "Space" in the sidebar, a "Project" in settings and a "Board" in emails, with a trash icon that permanently deletes on first click.

**Good:** One word, "Project", everywhere. Deleted projects go to Trash, stay for 30 days and can be restored, which is what the trash metaphor promises.

## When laws conflict

- Against novelty and brand voice: clear names win over clever ones. If a label needs explaining, it is the wrong label.
- With Jakob's Law and Mental Model: the conceptual model is what you present; the mental model is what people bring. When they differ, change what you present, or bridge the gap in context. Do not expect people to change.
- Against Tesler's Law (hide complexity): hide mechanism, not consequences. People can be spared how sync works, but they must know whether their change reached other people.

## Origin

Don Norman treats the conceptual model as the principle that ties the others together in The Design of Everyday Things: affordances, signifiers, constraints, mapping and feedback are how a product communicates its model.

Cite as: Don Norman, The Design of Everyday Things (1988, revised 2013).
