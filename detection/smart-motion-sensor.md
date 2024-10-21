# Smart Motion Sensor

## Setup

Scrypted can create a `Smart Motion Sensor` to report when a object is detected on a camera. This feature can be used with supported cameras that report smart detection events or [Scrypted NVR Object Detection](/scrypted-nvr/).

1. Install the `Video Analysis Plugin`.
2. Click `Add New`.
3. Select a camera to create a sensor.
4. Select the desired detections to report.
5. This sensor can be synced to other platforms to be used within automations.

::: tip
When using Smart Motion Sensor with detections from Scrypted NVR (and supported camera plugins like Unifi), the sensor can also provide a snapshot of the most recent event.
:::

<ImagePopup src="/img/smart-motion-sensor.png"></ImagePopup>

## License Plate Recognition

Scrypted can create a `Smart Motion Sensor` that triggers on specific license plates. This feature requires camera hardware with native LPR support (Unifi AI Cameras) or via software with Scrypted NVR Object Detection. License Plate Recognition is *highly* dependent on lighting conditions, vehicle speed, camera angle, and video quality. Refer to the manufacturers documentation for optimal setup.

### Scrypted NVR Setup

When using Scrypted NVR, license plate recognition must first be enabled on the camera. Be aware that this will use reduce the camera's overall detection performance to also accomodate license plate recognition:

1. Navigate to the camera in the Scrypted Management Console.
2. Click the Object Detection Settings.
3. Add `plate` to the detection list.
4. Click `Save`.

### LPR Sensor Setup

1. Set up a smart motion sensor as described in the steps above.
2. In the Detection dropdown, select `plate` (Scrypted NVR) or `licensePlate` (Unifi). The `vehicle` or `car` detection type will not work, as that detects the entire vehicle and not specfically the license plate.
3. Navigate to the `Recognition` tab.
4. Type the license plate to detect. Press enter to add it to the list. Multiple license plates may be provided, repeat this process for as many plates are desired.
5. Click `Save`.

<ImagePopup src="/img/lpr.png"></ImagePopup>

::: tip
License plate character recognition can be inaccurate depending on conditions. Changing the `Label Distance` setting will configure the detector to allow a number of missing or incorrect characters when attempting to match a specific plate.  Ie, a distance of 1 will match `ABCDE` to `ABCBE` or `ABCD`.
:::

## Face Recognition

Scrypted can create a `Smart Motion Sensor` that triggers on specific people. This feature requires requires Scrypted NVR Object Detection (currently no camera/plugin supports this on hardware). Face Recognition is *highly* dependent on lighting conditions and face capture angle.

### Scrypted NVR Setup

When using Scrypted NVR, label some faces in the Detections overview tab to start recognizing the people of interest.

### Face Recognition Sensor Setup

1. Set up a smart motion sensor as described in the steps above.
2. In the Detection dropdown, select `face` (Scrypted NVR). The `person` detection type will not work, as that detects the entire person and not specfically the face.
3. Navigate to the `Recognition` tab.
4. Type the name of person to detect as labeled in the prior step. Press enter to add it to the list. Multiple names may be provided, repeat this process for as many people are desired.
5. Set the `Label Distance` to `0` so the name must exactly match.
6. Click `Save`.

<ImagePopup src="/img/face.png"></ImagePopup>
