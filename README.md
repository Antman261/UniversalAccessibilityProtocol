# Universal Accessibility Protocol
The purpose of the Universal Accessibility Protocol (UAP) is to make every day devices, especially those in public spaces, accessible to anyone with a physical disability. The UAP aims to achieve this by defining a standard protocol for devices to wirelessly broadcast actions that nearby users can call.

## Example
Imagine a lift, to operate it, an able bodied person would:

1. Press the up or down button outside the lift
2. Enter the lift and select their floor
3. Optionally hold the door open for someone

However for a person with limited upper mobility many of these steps might be hard, if not impossible. Plus designing physical interfaces for a wide range of access scenarios is difficult - hand rails for one person might prevent someone in a wheelchair getting close enough to reach the buttons. What would be ideal, is if the interface was customised to the access requirements of each person. This is what the UAP enables.

For a person with limited mobility accessing the same lift:
(Via smartphone app in this example)

1. Approach lift and open app
2. App receives call actions: `['Up', 'Down']`
3. User makes selection and the lift is called
4. Enter lift and app receives list of available floors: `['B', 'G', '1', '2', '3', '4']`, 
5. User makes selection and the lift travels to the selected floor

Additionally, it could broadcast miscellaneous actions: `['Doors Open', 'Emergency Stop', 'Emergency Telephone']`

These same steps could be carried out by _any_ client device implementing the UAP. It might not necessarily be a smartphone, it could be any custom made device implementing client-side UAP.

## Advantages
### Interface Polymorphism
A device broadcasting UAP actions can have these actions displayed in any type of interface, including non-visual ones, voice controlled, spoken, tactile, etc. Any interface capable of stepping up or down a decision tree and selecting elements can call actions of a UAP broadcast device. So in short, even a device that loops through options and only requires a user to make a single selection should be able to call actions for a UAP broadcaster.

### Localisation
Available actions for a broadcast device should be pieced together from pre-defined actions in the UAP specification. This means that a broadcast device will always have its actions displayed in the user's preferred language. This limitation to predefined actions is what also enables interface polymorphism.

### Locality
Using short range technologies should limit access to devices to people within the physical area of the broadcast device. This is NOT an IoT application and internet connectivity should never be a requirement.

### Action Parity
Any device broadcasting UAP should make the available actions identical to those physically available. The device itself should not need to know if someone pressed a physical button or used UAP.


## Requirements
Broadcast devices should not create unnecessary steps prior to calling an action. This means no need to log in, no need to connect to a network, nor accept terms of use. Broadcast devices should also not be accessible over the internet. This makes Bluetooth a better candidate than Wifi.

Broadcast devices also need to be able to communicate a decision tree of actions, some of which may be named and some of which may be an ordered list of actions. This means we need dictionaries and arrays. Well we get these things for with JSON, plus a more human readable form with YAML, and nearly every language has tools to parse, transform, and serialize JSON.

## Glossary

#### Broadcast Device

A device which is making its physical features accessible via the UAP. For example, a lift.

#### Client Device

A device used by someone with a disability to access and command broadcast devices. For example, a smartphone app.

#### Action

Actions that can be performed on or by objects in the world. For example, "Open doors".

#### Actionable Nouns

Names of common things that will be used as an action in broadcast devices. A clear example of this is a lift with the destination `Basement`.

## Further reading

- [Latest schema definition](https://github.com/Antman261/UniversalAccessibilityProtocol/tree/master/schemas/v0.0.1)
- [Example: Lift](https://github.com/Antman261/UniversalAccessibilityProtocol/blob/master/schemas/v0.0.1/examples/lift.md)
- [Example: Train](https://github.com/Antman261/UniversalAccessibilityProtocol/blob/master/schemas/v0.0.1/examples/train.md)
- [Guideline: Broadcast devices](https://github.com/Antman261/UniversalAccessibilityProtocol/blob/master/guidelines/broadcast_devices.md)

## Contributing
UAP requires a well defined set of actions and well defined use cases for its 1.0 spec.
It also needs a hardware proof of concept, its own `"Hello world!"` if you will.

If you feel capable of contributing either of these things then make sure to get involved! Submit an issue, pull request, or suggestion.
