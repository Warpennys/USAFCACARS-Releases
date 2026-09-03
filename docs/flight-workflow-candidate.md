# Flight workflow candidate testing

This describes unreleased development work, not the public 1.1.5 installer.

The intended sequence is: select/prepare a flight, Load Flight to Planner, then
Start Flight after MSFS confirms the load. Start should flash only at that point.
Active tracking reads FLIGHT STARTED with a steady light. Unavailable actions stay
visible but disabled/unlit. Direct loading remains an alternative. End/File should
indicate readiness only after flying, landing and stopping.

Cancel must cancel tracking without filing a PIREP and return MSFS to its planner.
An incomplete planner return must be reported, not called successful; Cancel can
retry that return without repeating the already completed tracking cancellation.

Build/readiness contracts pass. **The MSFS planner-return timeout remains under
investigation; live acceptance has not passed.** Do not promote this candidate to
the automatic update feed yet. Test Open, Scheduled, Tour and approved Charter
bids, plus Free Flight, SimBrief and imported plans, including changed selections,
failed loads, repeated clicks, cancellation/retry, and physical flight controls.

If a planner return fails, retain the exact message and its reported camera state.
Do not reinstall MSFS, remove controller bindings or clear caches as a substitute
for investigating that transition.

Controls diagnostics now distinguish command transmission from observed release
of slew and position/attitude freezes. Automated verification covers delayed and
failed confirmation. A read-only live snapshot is available, but neither that
snapshot nor software-injected inputs prove physical stick/yoke operation.
