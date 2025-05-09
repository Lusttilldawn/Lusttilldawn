# file: bondage_education_app.py

class BondageTechnique:
    def __init__(self, name, difficulty, description, steps, safety_notes):
        self.name = name
        self.difficulty = difficulty
        self.description = description
        self.steps = steps
        self.safety_notes = safety_notes

    def display_summary(self):
        print(f"\nTechnique: {self.name}")
        print(f"Difficulty: {self.difficulty}")
        print(f"Description: {self.description[:120]}...")

    def display_full(self):
        print(f"\n=== {self.name.upper()} ===")
        print(f"Difficulty: {self.difficulty}")
        print(f"Description: {self.description}\n")
        print("Steps:")
        for i, step in enumerate(self.steps, 1):
            print(f"  {i}. {step}")
        print("\nSafety Notes:")
        for note in self.safety_notes:
            print(f"  - {note}")
        print("="*40)


def load_techniques():
    return [
        BondageTechnique(
            name="Single Column Tie",
            difficulty="Beginner",
            description="Used to tie a single limb or anchor rope to an object. It's foundational and used in many forms.",
            steps=[
                "Form a bight and place it over the wrist or object.",
                "Wrap the working end twice around the column.",
                "Thread the tail through the bight and cinch.",
                "Finish with a square knot or backup knot."
            ],
            safety_notes=[
                "Check for proper circulation regularly.",
                "Avoid tying too tightly or over joints.",
                "Ensure you have safety scissors nearby."
            ]
        ),
        BondageTechnique(
            name="Double Column Tie",
            difficulty="Intermediate",
            description="Used to bind two limbs together, e.g., wrists or ankles. Great for immobilization while keeping comfort.",
            steps=[
                "Hold wrists/ankles together with slight gap.",
                "Wrap rope 2–3 times around both limbs.",
                "Pull through and cinch between the limbs.",
                "Tie off using secure knots away from pressure points."
            ],
            safety_notes=[
                "Avoid excessive tension between limbs.",
                "Ensure balance in body position.",
                "Test for numbness or tingling every few minutes."
            ]
        ),
        BondageTechnique(
            name="Chest Harness (Takate Kote)",
            difficulty="Advanced",
            description="A foundational upper-body harness, popular in Japanese rope bondage. Requires precision and anatomical awareness.",
            steps=[
                "Create a double wrap around the upper chest.",
                "Secure the upper arms behind the back.",
                "Add tension lines between wraps.",
                "Lock off and dress the rope aesthetically."
            ],
            safety_notes=[
                "Do NOT compress the brachial plexus area.",
                "Monitor upper arm for signs of nerve compression.",
                "Always tie with full consent and understanding."
            ]
        )
    ]


def show_menu():
    print("\nBondage Tactics Educational App")
    print("1. View all techniques")
    print("2. View safety overview")
    print("3. Exit")


def safety_overview():
    print("\n=== SAFETY FIRST ===")
    print("1. Always obtain informed, enthusiastic consent.")
    print("2. Use safety scissors in case of emergency.")
    print("3. Avoid tying over joints or compressing nerves.")
    print("4. Communicate constantly with your partner.")
    print("5. Educate yourself thoroughly before practicing.")
    print("="*40)


def main():
    techniques = load_techniques()

    while True:
        show_menu()
        choice = input("\nEnter your choice: ").strip()

        if choice == "1":
            print("\nAvailable Techniques:")
            for idx, tech in enumerate(techniques, 1):
                print(f"{idx}. {tech.name}")
            sel = input("Choose a technique number to view details: ").strip()
            if sel.isdigit() and 1 <= int(sel) <= len(techniques):
                techniques[int(sel)-1].display_full()
            else:
                print("Invalid selection.")
        elif choice == "2":
            safety_overview()
        elif choice == "3":
            print("Goodbye. Practice responsibly.")
            break
        else:
            print("Invalid input. Try again.")


if __name__ == "__main__":
[
  {
    "name": "Single Column Tie",
    "difficulty": "Beginner",
    "description": "Used to tie a single limb or anchor rope to an object. It's foundational and used in many forms.",
    "steps": [
      "Form a bight and place it over the wrist or object.",
      "Wrap the working end twice around the column.",
      "Thread the tail through the bight and cinch.",
      "Finish with a square knot or backup knot."
    ],
    "safety_notes": [
      "Check for proper circulation regularly.",
      "Avoid tying too tightly or over joints.",
      "Ensure you have safety scissors nearby."
    ]
  },
  {
    "name": "Double Column Tie",
    "difficulty": "Intermediate",
    "description": "Used to bind two limbs together, e.g., wrists or ankles. Great for immobilization while keeping comfort.",
    "steps": [
      "Hold wrists/ankles together with slight gap.",
      "Wrap rope 2–3 times around both limbs.",
      "Pull through and cinch between the limbs.",
      "Tie off using secure knots away from pressure points."
    ],
    "safety_notes": [
      "Avoid excessive tension between limbs.",
      "Ensure balance in body position.",
      "Test for numbness or tingling every few minutes."
    ]
  }
]

    main()