# Keyboard Event Key Types

## Description

A simple Typescript package that contains the types of the keyboard-event-key as string-literals like: ArrowDown, ArrowUp and so on.

### Fork

This is a fork of [@Moh-Snoussi/keyboard-event-key-type](https://github.com/Moh-Snoussi/keyboard-event-key-type).

Intellisense is fixed by applying the suggestion from [issue 1](https://github.com/Moh-Snoussi/keyboard-event-key-type/issues/1).

Use the original `KeyboardEventKey` type if you wish for Intellisense autocomplete when writing the key name, but wish to accept custom keys. If you enter an invalid key name, you will not get a TS error.

An additional type `KnownKeyboardEventKey` has been added. This type does not allow custom keys, meaning you will get a TS error if you write an invalid key name. This fixes [issue 3](https://github.com/Moh-Snoussi/keyboard-event-key-type/issues/3).

## Getting Started

### Installing

```shell
npm install --save keyboard-event-key-type
```

### Usage

```typescript
document.addEventListener("keydown", function (event) {
  const actualKey = <KeyboardEventKey>event.key;
  const actionKey: KeyboardEventKey = "ArrowDown"; // <- intellisense
  if (actualKey === actionKey) {
    // clicked !
  }
});
```

#### IntelliSense

The package mainly helps with the IDE-IntelliSense:
![Alt text](readme_img/IntelliSense.jpg?raw=true "IntelliSense")

## Supported types

All keys are taken from [developer.mozilla.KeyboardEvent.Keys](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/key/Key_Values) as of 11/19/2021,
with additional support to custom keys.

- NumericKeypadKeys
- UpperAlpha
- LowerAlpha
- ModifierKeys
- WhitespaceKeys
- NavigationKeys
- EditingKeys
- UIKeys
- DeviceKeys
- IMECompositionKeys
- LinuxDeadKeys
- FunctionKeys
- PhoneKeys
- MultimediaKeys
- TVControlKeys
- MediaControllerKeys
- SpeechRecognitionKeys
- DocumentKeys
- ApplicationSelectorKeys
- BrowserControlKeys
- KoreanKeyboardsOnly
- DeprecatedWhitespaceKey
- SpecialValueKey
- CustomValueKey
