# `@remote-ui/dom-client`

Implements a subset of the HTML DOM on top of [`@remote-ui/core`'s `ReactRoot`](../core#remoteroot).

## Installation

Using `yarn`:

```
yarn add @remote-ui/dom-client
```

or, using `npm`:

```
npm install @remote-ui/dom-client --save
```

## Usage

`@remote-ui/dom-client` provides one function: `createDocument()` takes a [`@remote-ui/core` `RemoteRoot`](../core#remoteroot), and returns a [Document](https://developer.mozilla.org/en-US/docs/Web/API/Document) instance. The Document instance has a `.body` property that can be used to render content in the remote-ui host.

```ts
import {createRemoteRoot} from '@remote-ui/core';
import {createDocument} from '@remote-ui/htm';

const root = createRemoteRoot(() => {});
const document = createDocument(root);

const button = document.createElement('ui-button');
button.setAttribute('primary');
button.addEventListener('press', () => console.log('Button pressed!'));
button.textContent = 'Submit';
document.body.append(button);
```
