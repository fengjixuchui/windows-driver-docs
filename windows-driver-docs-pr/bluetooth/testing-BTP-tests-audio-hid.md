---
title: Microsoft Bluetooth Test Platform - Audio and HID scenario tests
description: Bluetooth Test Platform (BTP) Audio and HID Scenario tests.
ms.assetid: b5b039bb-af0f-446f-9657-aa0e137a3437
ms.date: 2/14/2020
ms.localizationpriority: medium

---

# BTP Audio and HID Scenario Tests #

The BTP audio and HID tests will test the ability of the local system to pair with both a HID and an Audio device and use these two devices simultaneously.

## Setting Up ##

When using a radio with the Traduci, first check that the green power indicator, an optional yellow test LED, and 3 orange LEDs on the Traduci are on. Confirm that the SUT's Bluetooth radio is powered on and that the appropriate radio(s) are correctly plugged in to the Traduci. Currently the RN52 radio can **only** be plugged into JA. Similarly the Bluefruit radio can **only** be plugged into JC. More detailed information on setting up can be found at [Setting up BTP](testing-BTP-setup.md).

When using the BM-64-EVB, two red LEDs should be on (one of which may turn off after a bit). Confirm the switches, jumpers, and ports are configured for testing as decribed in the [BM-64-EVB board overview](testing-BTP-hw-bm64.md#getting-started). 

Features and purchasing information for supported radios can be found at [Supported BTP Hardware](testing-BTP-hw.md).

## Running the Audio and HID Scenario Tests ##

Navigate to the folder where the BTP package was extracted. It will typically be under `C:\BTP`. In a folder named after the version of the package, you will find the scripts referenced below. Then run either:

- `RunAudioHidScenarioTests.bat <audio radio name> <hid radio name>` from an elevated command prompt or
- `RunAudioHidScenarioTests.ps1 <audio radio name> <hid radio name>` from an elevated PowerShell console

Information on available radio name parameters can be found [here](testing-BTP-hw.md#supported-radios).

You can also include the optional parameter `-VerboseLogs` at the end to get a more verbose output of inner operations of BTP.

When using the Traduci, as a test starts the red LED next to the 12 pin adapter will turn on once the command from the test to power the radio has been sent. This LED will be turned off at the end of every test. If it is on at the start of the next test due the previous test failing, we will attempt to power it down and power it back on to return it to a known state. If the power cycle fails, the test will fail due to the radio being in an unknown state.

When using the BM-64-EVB, red and blue LEDs will flash in patterns for indicting steps of the process such as powering on, pairing, and playing audio. 

## Capturing Logs ##

To capture the Bluetooth logs, follow the instructions for the [busiotools for Windows Repo on GitHub](https://github.com/microsoft/busiotools/blob/master/bluetooth/tracing/readme.md).

## Known issues ##

- Stress tests: Tests run in a tight loop using an LE radio may cause pairing or unpairing to fail.