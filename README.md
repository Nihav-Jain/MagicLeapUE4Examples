# Magic Leap UE4 Examples

This repository contains an Unreal Engine project for Magic Leap feature examples. The tip of the `main` branch needs to be used with the tip of the `dev-lumin` branch of the Unreal Engine fork from https://github.com/Nihav-Jain/UnrealEngine. 

Make sure to set your own developer certificate in Project Settings > Magic Leap.

## Unreal Engine Fork for Magic Leap Development
Because I don't wanna make too many changes to the official README files of the Unreal Engine repo, I'll add the details about the changes in that repo over here.

### Branch : dev-lumin
#### Build
- Based off of the MLSDK 0.24.0 release of Magic Leap's custom Unreal Engine.
- Unreal Engine 4.24.3
- MLSDK 0.24.0 and above

#### Changelog
- Magic Leap Found Objects integration.
- Image track rework
    - Allow users to select normal axis for image tracker. The coordinate space conversions performed from C-API to Unreal invert
    the singularity of the resultant quaternion, which changes what the euler angles of the rotator represent. Fixing the direction of normal to match the world coordinate space axes also fixes the quat math allowing us to use just the Yaw for horizontal images. 
    - Delay tracker creation until first image is added.
    - Limit the mutex locks to the minimum possible scope, fix some bugs with potential nested mutex lock calls.
    - Mark some BP func lib getters as BlueprintPure.
    - Update MagicLeapAR impl for image tracking.
- Fix bug in MagicLeapRunnable where it dequeues the "completed"

## Feature Examples
- Found Objects : Queries Magic Leap's object recognition pipeline every 5 seconds and renders a bounding box aroung the found objects along with the label describing the object.

## Disclaimer
This is NOT an official Magic Leap project.

Note that neither this examples project nor the UnrealEngine fork mentioned above are officially supported by Magic Leap. These are just side projects from a dev who loves XR and loves Unreal Engine.
