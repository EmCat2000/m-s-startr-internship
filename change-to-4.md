my_notes = yaml.safe_load("""
- id: my-001
  source: my notes
  text: >-
    Two-minute rule: If a task takes under two minutes, do it now
    instead of writing it down.

- id: ms-002
  source: my notes
  text: >-
    Day-planer: Create a checklist at the beginning of the day.
    Throughout the day try to check things off.
    It's okay if you don't get everything done, and it's okay if you get things done that aren't on it
    It's just there to help you see your goals.

- id: ms-003
  source: my notes
  text: >-
    Jurnal: Jurnal every day, talk about anything and everything you want.
    All that is important is keeping a date in it, and not having a gap for longer than 1 day.
    it helps with two things:
    1. geting stress out
    2. haveing notes about things that hapend or that are going to hapen

- id: ms-004
  source: my notes
  text: >-
    Alarms: If you are ever forgeting due dates, set alarms and timers.
    They will allow you to not have to focus on the exact time of stuff you need to get done, and insted get them done.

- id: ms-005
  source: my notes
  text: >-
    If you have a big task break it up into smaller more manageable task.
    Tasks small enough that they are silly how small they are.
    You can also then put them in a checklist, and see check after check like if they were a progres bar.

- id: ms-006
  source: my notes
  text: >-
    If you had somthing planed for the day, but you didn't get it done put it as a priority for the next day.
    Though prioritise it only if it is important enough, otherwhise just put it planed for the new day.

- id: ms-007
  source: my notes
  text: >-
    Build routins and habits.
    They alow you to not forget some things, and they let you get into the flow.
    It can be hard at first, but ataching one habit to a previeus one can make it easier, one step at a time.

- id: ms-008
  source: my notes
  text: >-
    Start your day of with a sucses, it doesn't mater how big or small.
    It can be anything evan just cleaning your room or making breakfast
    Just geting that little thing done first, alows you to get on path for doing things in the day.

# ✏️ add your own notes below, same shape.
#    Keep the two-space indent lined up, and leave a blank line
#    between notes. Use >- for any note that runs past one line.
""")

KB.extend(my_notes)
kb_texts = [note["text"] for note in KB]
kb_vectors = embed(kb_texts)
print(f"Index now holds {len(KB)} notes. Re-run Step 4 with a question your notes answer.")