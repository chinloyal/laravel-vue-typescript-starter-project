# Laravel + Vue + TypeScript Starte Project (MPA)

> Start project template of full stack web development

## Demo

> Screenshots of a demo application that uses this template

The live demo can be found [here](http://addb-bakery.herokuapp.com)
The repo for the demo can be found [here](https://github.com/chinloyal/addb-bakery)

![Splash Page Screenshot](https://i.imgur.com/NLvWg5Y.png)
![Login Page Screenshot](https://i.imgur.com/o24XaE4.png)
![Login GIF](https://i.imgur.com/zARWtD4.png)

## Features

-   Laravel 6.0
-   Vue.js 2.5
-   TypeScript
-   Vuetify (Material Design)
-   Reusable dialog
-   NProgress on axios request
-   Git Hooks
-   Vuex (with secure storage)

## Installation

> With composer

```bash
$ composer create-project --prefer-dist chinloyal/lavuet ProjectName
$ cd ProjectName
$ npm install
```

> From github

```bash
$ git clone https://github.com/chinloyal/lavuet.git ProjectName
$ cd ProjectName
$ composer install
$ npm install
$ cp .env.example .env
$ php artisan key:generate
```

## Usage

### Development

```bash
$ npm run watch # build and watch
$ npm run hot # serve with hot reload
```

### Production

```bash
$ npm run prod
```

### App Dialog

Firstly include the AppDialog component in your main layout blade file.
Now you can use the dialog from any component by accessing `$dialog` on your vue instance.

> Example

```ts
// Snippet of code
deleteItem() {
    this.$dialog.show({
        title: 'Confirm Delete',
        message: 'Are you sure you want to delete this item?',
        showCancelBtn: true,
        onConfirm() {
            // Delete item
        }
    })
}
```

Available Options on the app dialog

```
showCancelBtn?: boolean;
cancelBtnText?: string;
okBtnText?: string;
title: string;
message: string;
visible?: boolean;
dialogType?: string;
onConfirm?: Function;
```

'?' Means optional

### Secure Storage

If you have need to store data in local storage simply use the utility provided in the utils folder.

```ts
import { SecureStorage } from '@/utils/secure-storage';
const storage = SecureStorage.getInstance();

storage.set('key', 'value');
```

It uses localStorage but encrypts the data stored so it cannot be accessed from the console.

> NB: In your .env file for laravel set `MIX_APP_SECRET=my-secret-key` with a strong key.

## Note

-   This is not an SPA.
-   You can use vuetify components in blade files
