# ✏️ Your turn: edit the name, the cues, and the example. Keep cues as a list [ ] of short phrases. Then run the cell and see if your trap got caught.
my_trap = {
    "n": 11,
    "name": "dead rush",
    "cues": ["wait till deadline", "less than 10 minutes", "go faster", "no time to think"],
}

my_example = "I'm going to stay up all night so I can go faster and finish it sooner."

# --- You don't need to read below. It just checks your trap is shaped right, then tests it. ---
cues = my_trap.get("cues")
if not isinstance(cues, list) or not all(isinstance(c, str) for c in cues):
    print("✋ Almost — 'cues' needs to be a list in square brackets, like")
    print('   ["quick break", "check my phone"].  Fix that, then run this cell again.')
else:
    your_trap_fired = check_plan(my_example, traps=[my_trap])   # test ONLY your trap
    if your_trap_fired:
        print(f"✅ Your trap '{my_trap['name']}' caught your example. Nice work.")
    else:
        print(f"❌ Your trap '{my_trap['name']}' didn't catch your example yet — no worries.")
        print("   Tip: one of your cue phrases has to appear, word for word, in my_example.")
        print(f"   Your cues right now: {cues}")
    also = [t["name"] for t in check_plan(my_example, traps=TRAPS)]
    print(f"   (Starter traps that also matched your example: {also or 'none'}.)")