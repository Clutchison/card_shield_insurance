# Card Shield

Card Shield insures graded trading cards and keeps a verifiable record of what a collection holds and what it is worth. This glossary fixes the words we use for cards, coverage and the insurance chain so that conversations, issues and code all mean the same thing.

Terms below are industry-standard meanings, seeded from `docs/research/2026-11-02-card-shield-market-research.md`. Card Shield–specific terms get added as grill sessions resolve them.

## People and accounts

**User**:
A person with a Card Shield account, paying or not.
_Avoid_: Customer, account, collector (when the account holder is meant)

**Member**:
A User who pays for a Card Shield membership.
_Avoid_: Subscriber, premium user, pro user

**Policyholder**:
A User who holds an insurance policy placed through Card Shield.
_Avoid_: Insured, customer, client

**Portfolio**:
The set of slabs a User tracks in Card Shield.
_Avoid_: Collection, inventory, vault

**High-value collector**:
A collector who holds $10k or more in slabs.
_Avoid_: Whale, serious collector, HNW collector

**Beneficiary**:
A person a User names to receive specific slabs from their Portfolio.
_Avoid_: Heir, designee, beneficiary designation (which implies a legal instrument)

**Card store**:
A business that sells cards from a permanent retail location, even if it also sells at shows.
_Avoid_: Card shop, hobby shop, LCS

**Table vendor**:
A dealer who sells cards from a rented table at shows and has no permanent retail location.
_Avoid_: Dealer (too broad), show vendor, booth vendor

## Cards and grading

**Grader**:
A company that authenticates a card, assigns it a condition grade and seals it in a slab (PSA, SGC, BGS, CGC, TAG).
_Avoid_: Grading service, authenticator, grading house

**Slab**:
A graded card sealed in a grader's tamper-evident plastic case with a label showing the card, grade and cert number.
_Avoid_: Graded card (when the physical object is meant), case, holder

**Cert number**:
The unique identifier a grader prints on a slab's label, which can be checked against that grader's registry.
_Avoid_: Serial number, certificate ID, cert ID

**Raw card**:
A card that has not been graded and is not in a slab.
_Avoid_: Ungraded card, loose card

**Submission**:
A batch of raw cards sent to a grader to be graded.
_Avoid_: Order, grading order

**Comp**:
A recent sale of the same card at the same grade from the same grader, used as evidence of market price.
_Avoid_: Comparable, sold listing, price point

## Coverage

**Agreed value**:
A coverage basis where the insurer and insured fix an item's value up front, and that amount (less deductible) is paid on a total loss.
_Avoid_: Stated value, guaranteed value

**Market value**:
A coverage basis where a loss is paid at what the item would sell for at the time of the claim.
_Avoid_: Fair market value (FMV), actual cash value (ACV, which deducts depreciation)

**Declared value**:
The value a sender states for an item when shipping it or submitting it to a grader, which caps what the grader or shipper will reimburse.
_Avoid_: Insured value, max insured value

**Scheduled item**:
An item individually listed on a policy with its own value.
_Avoid_: Listed item, itemized item

**Blanket coverage**:
Coverage for a whole collection up to a total limit, without listing each item.
_Avoid_: Unscheduled coverage, collection coverage

**Sublimit**:
A cap inside a broader policy on what it will pay for a category of property, such as trading cards under a homeowners policy.
_Avoid_: Special limit, inner limit

**Mysterious disappearance**:
Loss of an item with no known cause or evidence of theft.
_Avoid_: Unexplained loss, lost item

## Insurance chain

**Carrier**:
The licensed insurance company that issues the policy and bears the risk.
_Avoid_: Insurer (fine in prose, but use Carrier in issues and code), underwriter, paper

**MGA**:
A managing general agent: a firm a carrier has delegated authority to underwrite and bind policies on the carrier's behalf.
_Avoid_: Program administrator, managing agent

**Producer**:
A person or agency licensed to sell, solicit or negotiate insurance, paid by commission.
_Avoid_: Agent, broker (unless the distinction matters)

**Appointment**:
A carrier's or MGA's formal authorization for a producer to sell its products.
_Avoid_: Contract, carrier relationship

## Estate

**Separate writing**:
A signed list of tangible personal property and who should receive it, referenced by a will and updatable without re-executing the will (UPC §2-513, where a state has adopted it).
_Avoid_: Beneficiary designation, TOD (cards generally cannot carry one)
