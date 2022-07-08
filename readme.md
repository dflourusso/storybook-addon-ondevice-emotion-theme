# storybook-addon-ondevice-emotion-theme

Storybook-addon-ondevice-emotion-theme for react-native can be used to provide themes to your components that are built with emotion. You can choose between themes in `Themes` panel on your device. This addons wraps every story with `ThemeProvider` from `@emotion/react`.

## Installation

```sh
yarn add -D storybook-addon-ondevice-emotion-theme
```

## Configuration

Create a file called `rn-addons.js` in your storybook config.

Add following content to it:

```js
import 'storybook-addon-ondevice-emotion-theme/register'
```

Then import `rn-addons.js` next to your `getStorybookUI` call.

```js
import './rn-addons'
```

## Usage

```js
import React from 'react'
import { Text } from 'react-native'
import { storiesOf, addDectorator } from '@storybook/react-native'
import { withTheme } from 'storybook-addon-ondevice-emotion-theme'

addDecorator(withTheme)

storiesOf('Component', module)
  .addParameters({
    themes: [
      { name: 'theme1', colors: { primary: '#222222' } },
      { name: 'theme2', colors: { primary: '#eeeeee' } }
    ]
  })
  .add('default', () => <Text>Some Text</Text>)
```

or globally in storybook.js

```js
import React from 'react'
import { addDecorator, addParameters } from '@storybook/react-native'
import { withTheme } from 'storybook-addon-ondevice-emotion-theme'

addDecorator(withTheme)

addParameters({
  themes: [
    { name: 'theme1', colors: { primary: '#222222' } },
    { name: 'theme2', colors: { primary: '#eeeeee' } }
  ]
})
```
