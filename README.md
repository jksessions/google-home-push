# google-home-push
Send push notifications to your Google Home device.

## Installation
```
$ npm install --save google-home-push
```

## Usage
```
const GoogleHome = require("google-home-push");

// Pass the name or IP address of your device
const myHome = new GoogleHome("Living Room Home");

myHome.speak("Hello world!");
myHome.push("https://example.com/music.mp3");
```

## Example
### Using different languages
```
let options = {
    language: "ko"
};

const myHome = new GoogleHome("192.168.0.1", options);
myHome.speak("안녕하세요!");           // Will speak in Korean as it follows the options
myHome.speak("Bonjour!", "fr");     // Will speak in French as the optional language argument is passed
```
Pass the `language` option from the [following list](https://cloud.google.com/translate/docs/languages). The default is set as English.

## API
### new GoogleHome(deviceIdentifier, [options])
Creates an `instantce` of GoogleHome.

#### deviceIdentifier
Type: `string`
Accepts valid IP addresses or device name.

#### options
Type: `Object`

| Property | Type | Default | Description |
| --- | --- | --- | ---|
| language | string | `en` | Default language that would be used by the `.speak()` function |
| accent | string | `en` | Default accent that would be used by the `.speak()` function |

### .speak(message, [language])
#### message
Type: `string`
Text that would be notified using the Google TTS

#### language
Type: `string`
Language that would be used to TTS the message. If one is not passed, then it would fall back to one set in the options.
Pass the `language` option from the [following list](https://cloud.google.com/translate/docs/languages).

### .push(url)
#### url
Type: `string`
A valid media URL that would be cast

## License
[MIT](https://github.com/taeukme/google-home-push/blob/master/LICENSE.md)