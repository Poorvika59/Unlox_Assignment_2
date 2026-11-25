# 🧬 GroupDNA — your WhatsApp group chat, decoded

*Spotify Wrapped, but for your friend group.* A text-based analytics report for a WhatsApp chat export, built with **only Python fundamentals + NumPy**.

![output screenshot](screenshot.png) <!-- add a screenshot of your printed report here -->

## What it does
Parses `hostel_bois.txt` (a synthetic hostel group chat, 60 days, 3,174 messages, 6 members) and prints a screenshot-ready report:
group overview, busiest day/hour, a NumPy activity heatmap (participants × 24 hours), favourite words with block-character bars, response speed, longest silent streaks, and a personality archetype for every member (Spammer, Group Mom, Night Owl, Storyteller, Drama Queen, Ghost, Comedian, Question Master + my own 9th archetype, *The Pakka Punctual One*).

## Parser edge cases handled
System messages (counted, skipped) · `<Media omitted>` (counted per person, excluded from word/length stats) · deleted messages (separate counter) · multi-line messages (continuation lines appended) · empty lines · missing/empty files.

## Constraints
**Allowed:** Python fundamentals, lists/tuples/sets/dicts, `numpy`, `open()`, `datetime.strptime` + `timedelta`, string methods.
**Forbidden (not used):** pandas, matplotlib/seaborn/plotly, `collections.Counter/defaultdict`, `re`, any ML or WhatsApp-analyzer library.

## How to run
1. Open `GroupDNA_POORVIKA G K.ipynb` in Google Colab (or Jupyter).
2. Upload `hostel_bois.txt` next to the notebook (Colab: folder icon → `/content/`).
3. Runtime → Run all. The final report is printed by the *Feature 8* cell.

## Archetype tie-break rule
Score = metric ÷ threshold. Primary archetypes are assigned greedily from the highest score, each archetype and each person used once; anyone left gets the best free fallback archetype (Comedian / Question Master / Punctual One).

