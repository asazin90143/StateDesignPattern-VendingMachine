# StateDesignPattern-VendingMachine

**Problem:** A vending machine needs to manage different states, including "Idle", "ItemSelected", "Dispensing", and "OutOfOrder". Each state has specific rules and restrictions regarding allowed operations, and the vending machine has associated attributes like item inventory and balance.

**Requirements:**

**1. Idle State:**

* Allow item selection.
* Disallow dispensing items and inserting coins.

**2. ItemSelected State:**

* Allow inserting coins and dispensing items.
* Disallow item selection.

**3. Dispensing State:**

* Allow no operations.
* Automatically transition back to the "Idle" state after dispensing is complete.

**4. OutOfOrder State:**

* Disallow all operations.

**Current System:** The system currently relies on conditional statements within the `VendingMachine` class to check the machine state and determine valid actions. This approach becomes cumbersome and error-prone as the number of states and their associated logic grows.

**Implement the State Pattern to improve code maintainability and flexibility:**

**1. Define VendingMachine States:**

* Create separate classes representing different machine states: `IdleState`, `ItemSelectedState`, `DispensingState`, and `OutOfOrderState`.

**2. Implement State Interface:**

* Define an interface `VendingMachineState` with methods for common actions like `selectItem`, `insertCoin`, `dispenseItem`, and `setOutOfOrder`.

**3. Implement State Behaviors:**

* Each concrete state class implements the `VendingMachineState` interface, providing specific behavior for its respective state. For example, the `IdleState` class would allow item selection, while the `OutOfOrderState` wouldn't allow any operations.

**4. Update VendingMachine Class:**

* Include attributes for item inventory and balance.
* Remove state-specific logic from the `VendingMachine` class.
* Introduce a reference to the current `VendingMachineState` object.
* Delegate actions like `selectItem`, `insertCoin`, `dispenseItem`, and `setOutOfOrder` to the current state object through its corresponding methods.

**UML Class Diagram:**

*(Insert UML class diagram here.  Since I'm a text-based AI, I can't directly create images.  You can use a UML diagram tool like draw.io, Lucidchart, or PlantUML to create the diagram and then embed it in your README.  Make sure the diagram clearly shows the states, the interface, and the relationships between them.)*
