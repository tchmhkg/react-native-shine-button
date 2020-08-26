<h1 align="center">

<p align="center">
  <a href="https://www.npmjs.com/package/react-native-shine-button"><img src="http://img.shields.io/npm/v/react-native-shine-button.svg?style=flat" /></a>
  <a href="https://github.com/tchmhkg/react-native-shine-button/pulls"><img alt="PRs Welcome" src="https://img.shields.io/badge/PRs-welcome-brightgreen.svg" /></a>
  <a href="https://github.com/tchmhkg/react-native-shine-button#License"><img src="https://img.shields.io/npm/l/react-native-shine-button.svg?style=flat" /></a>
</p>

    ReactNative: Native Shine Button (Android/iOS)

If this project has helped you out, please support us with a star 🌟

</h1>

This library is a React Native bridge around native Siri wave animation:

| **[Android: ChadCSong/ShineButton](https://github.com/ChadCSong/ShineButton) & [iOS: imwcl/WCLShineButton](https://github.com/imwcl/WCLShineButton)** |
| ----------------------------------------------------------------------------------------------------------------------------------------------------- |


|                                 |
| ------------------------------- |
| <img src="./assets/hero.gif" /> |

## 📖 Getting started

`$ npm install react-native-shine-button --save`

## **RN61 >= RNBAS V2 >**

- Add `react-native-image-helper` to your app package.json

`$ npm install react-native-image-helper --save`

- Add `react-native-vector-icons` to your app package.json and configure it as per their installation steps

`$ npm install react-native-vector-icons --save`

- **iOS**

      	- Add the following to your `Podfile` -> `ios/Podfile` and run pod update:

      	```
      	  	use_native_modules!
        pod 'RNShineButton', :path => '../node_modules/react-native-shine-button/ios'

        use_frameworks!
        pod 'WCLShineButton',:git => 'https://github.com/tchmhkg/WCLShineButton.git', :branch =>'master'
      	```

- **Android**

Please add below snippet into your app `build.gradle`

```
allprojects {
    repositories {
        maven { url 'https://jitpack.io' }
    }
}
```

## **RN61 >= RNBAS V1 >**

> RN61+ please use `react-native-shine-button` V1 and above

- **iOS**

      	- Add the following to your `Podfile` -> `ios/Podfile` and run pod update:

      	```
      	  	use_native_modules!
        pod 'RNShineButton', :path => '../node_modules/react-native-shine-button/ios'

        use_frameworks!
        pod 'WCLShineButton',:git => 'https://github.com/tchmhkg/WCLShineButton.git', :branch =>'master'
      	```

- **Android**

Please add below snippet into your app `build.gradle`

```
allprojects {
    repositories {
        maven { url 'https://jitpack.io' }
    }
}
```

## **RN60 < RNBAS V1 <**

> RN60 below please use `react-native-bottom-action-sheet` V.0.\*

- `$ npm install react-native-shine-button --save`

- `$ react-native link react-native-shine-button`

- `$ react-native link react-native-vector-icons`

#### Android

- Please add below snippet to `defaultConfig` in your app `build.gradle`file. This is with respect to [ISSUE: 1](https://github.com/tchmhkg/react-native-shine-button/issues/1):

```
jackOptions {
    enabled true
}
```

- Please add below snippet above `dependencies` in your app `build.gradle`:

```
buildscript {
    repositories {
        jcenter()
        google()
        maven { url "https://jitpack.io" }
    }

}

allprojects {
    repositories {
        jcenter()
        google()
        maven { url "https://jitpack.io" }
    }
}
```

> **Note:** This library is supported on Android SDK 27 > above

#### iOS

- After `react-native link react-native-shine-button`, please verify `node_modules/react-native-shine-button/ios/` contains `Pods` folder. If does not exist please execute `pod install` command on `node_modules/react-native-shine-button/ios/`, if any error => try `pod repo update` then `pod install`
- After verification, open your project and create a folder 'RNShineButton' under Libraries.
- Drag `node_modules/react-native-shine-button/ios/pods/Pods.xcodeproject` into RNShineButton, as well as the RNShineButton.xcodeproject if it does not exist.
- Add the `WCLShineButton.framework` into your project's `Embedded Binaries` and make sure the framework is also in linked libraries.
- Go to your project's `Build Settings -> Framework Search Path` and set `$(inherited) to recursive`.

  <img src="assets/setup.gif" />

## 💻 Usage

```javascript
import RNShineButton from 'react-native-shine-button'
;<RNShineButton
  shape={'heart'}
  color={'#808080'}
  fillColor={'#ff0000'}
  size={100}
/>
```

## Icons

- **RN Vector Icons:** It supports [react-native-vector-icons](https://github.com/oblador/react-native-vector-icons) library. Please find below snippet for the usage:

```javascript
import RNShineButton from 'react-native-shine-button'
import Icon from 'react-native-vector-icons/FontAwesome'

let music = <Icon family={'FontAwesome'} name={'music'} color={'#808080'} />

;<RNShineButton
  shape={music}
  color={'#808080'}
  fillColor={'#ff0000'}
  size={100}
/>
```

> **Note:**
>
> - We have added `family` prop for `Icon` class, please make sure that you pass the props

- **Custom Icons**

> **Note:**
> Since we are using native libraries, we have not found a solution in order to render RN Images in production, therefore please copy all your image assets in platform specific folders:

- Android: Please copy your image assets in app resource drawable folder
- iOS: Please copy your image assets in app resources folder

> Please refer example application for the image usage.

## 💡 Props

| Prop        | Type                                  | Default | Note                                                                                                                         |
| ----------- | ------------------------------------- | ------- | ---------------------------------------------------------------------------------------------------------------------------- |
| `shape`     | `string OR react-native-vector-icons` |         | The type of Shine Button you want. It's props are heart, like, star, smile. Even you are specify a react-native-vector-icons |
| `color`     | `string: HEX-COLOR`                   |         | Color which you want then the Shine Button is not active                                                                     |
| `fillColor` | `string: HEX-COLOR`                   |         | Fill Color then the Shine Button is clicked                                                                                  |
| `size`      | `number`                              |         | Size of Shine Button                                                                                                         |  |
| `disabled`  | `bool`                                |         | Disabling the Shine Button                                                                                                   |  |
| `value`     | `bool`                                |         | Default value whether it is selected or not                                                                                  |
| `onChange`  | `func`                                |         | It is invoke then the value of shine button is change                                                                        |

## ✨ Credits

- Android lib [ChadCSong/ShineButton](https://github.com/ChadCSong/ShineButton) Android implement.
- iOS lib [imwcl/WCLShineButton](https://github.com/imwcl/WCLShineButton) iOS implement

## 🤔 How to contribute

Have an idea? Found a bug? Please raise to [ISSUES](https://github.com/prscX/react-native-bottom-action-sheet/issues).
Contributions are welcome and are greatly appreciated! Every little bit helps, and credit will always be given.

## 💫 Where is this library used?

If you are using this library in one of your projects, add it in this list below. ✨

## 📜 License

This library is provided under the Apache License.

RNShineButton @ [prscX](https://github.com/prscX)

## 💖 Support my projects

I open-source almost everything I can, and I try to reply everyone needing help using these projects. Obviously, this takes time. You can integrate and use these projects in your applications for free! You can even change the source code and redistribute (even resell it).

However, if you get some profit from this or just want to encourage me to continue creating stuff, there are few ways you can do it:

- Starring and sharing the projects you like 🚀
- If you're feeling especially charitable, please follow [prscX](https://github.com/prscX) on GitHub.

  <a href="https://www.buymeacoffee.com/prscX" target="_blank"><img src="https://www.buymeacoffee.com/assets/img/custom_images/orange_img.png" alt="Buy Me A Coffee" style="height: auto !important;width: auto !important;" ></a>

  Thanks! ❤️
  <br/>
  [prscX.github.io](https://prscx.github.io)
  <br/>
  </ Pranav >
