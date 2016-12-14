# Lift Examples

Destinations can consist of either an array of named levels, or an object with named arrays.

An array under `destinations` can include n-many integers.

Directive `Go` is a toggle command used for lifts servicing only two levels.

Lifts requiring an unconscious disengage mechanism, directives and destinations can require press and hold. This is common in lifts without a fully enclosed capsule.

#### Lift 1
```
{
  "destinations": [
    "Basement", "Ground", 1, 2, 3
  ],
  "directives": [
    "Doors open", "Doors close"
  ],
  "emergency": [
    "Stop", "Call"
  ]
}
```

This lift makes use of the array form of destinations and is quite simple.

#### Lift 2
```
{
  "destinations": {
    "basement_levels": [1, 2],
    "main_levels": [1, 2, 3, 4, 5, 6, 7, 8, 9, 10],
    "carpark_levels": [1, 2, 3]
  },
  "directives": [
    "Doors open", "Doors close", "Up", "Down", "Go"
  ],
  "emergency": [
    "Stop", "Call"
  ]
}
```

This lift makes use of the object form of destinations. It simplifies accessing a large number of floors.

#### Lift 3
```
{
  "directives": [
    "Doors open", "Doors close", "Go"
  ],
  "emergency": [
    "Stop", "Call"
  ]
}
```

This is the simplest lift, servicing just two levels it makes use of `Go` as a toggle.
