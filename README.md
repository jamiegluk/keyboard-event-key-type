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
npm install --save-dev @jamiegluk/keyboard-event-key-type
```

### Usage

#### `KeyboardEventKey`

```ts
const actionKey: KeyboardEventKey = "ArrowUp"; //<- IntelliSense
const customKey: KeyboardEventKey = "CustomKey"; //<- Permitted
```

#### `KnownKeyboardEventKey`

```ts
const actionKey: KnownKeyboardEventKey = "ArrowUp"; //<- IntelliSense
const invalidKey: KnownKeyboardEventKey = "InvalidKey"; //<- Error
```

#### Example

```ts
document.addEventListener("keydown", (event) => {
  const actualKey = event.key as KeyboardEventKey;
  const actionKey: KeyboardEventKey = "ArrowDown"; // <- IntelliSense
  if (actualKey === actionKey) {
    // clicked !
  }
});
```

#### IntelliSense

The package helps with IntelliSense in your IDE: \
![Code example showing IntelliSense dropdown with a list of know keyboard keys, in VS Code](readme-intellisense.png?raw=true)

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
