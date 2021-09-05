# Rails Tailwind template

Quickly generate a rails app with Tailwind css library, Vue.js framework, and the gem devise.

# Get started

## Minimal (avalaible soon)
Get a minimal rails app ready to be deployed on Heroku with Tailwind, Simple form and debugging gems.

```sh
$ rails new \
  --database postgresql \
  --webpack \
  -m https://raw.githubusercontent.com/lioruby/rails-vue-tailwind-template/master/minimal.rb \
  CHANGE_THIS_TO_YOUR_RAILS_APP_NAME
```

### Minimal with rspec, factory_bot and shoulda-matchers gems (avalaible soon)
```sh
$ rails new \
  --database postgresql \
  --webpack=vue \
  -m https://github.com/Lioruby/rails-vue-tailwind-template/master/minimal.rb \
  CHANGE_THIS_TO_YOUR_RAILS_APP_NAME
```

## Devise
Same as minimal plus a Devise install with a generated User model.

```sh
$ rails new \
  --database postgresql \
  --webpack \
  -m https://raw.githubusercontent.com/lioruby/rails-vue-tailwind-template/master/devise.rb \
  CHANGE_THIS_TO_YOUR_RAILS_APP_NAME
```

### Devise with rspec, factory_bot and shoulda-matchers gems (avalaible soon)
it generate a spec directly for the user model

```sh
$ rails new \
  --database postgresql \
  --webpack \
  -m https://raw.githubusercontent.com/lioruby/rails-vue-tailwind-template/master/devise_rspec_factory_bot.rb \
  CHANGE_THIS_TO_YOUR_RAILS_APP_NAME
```

### Use
With this configuration, you will be able to use Vue components in your .erb file, as html element:

Create a vue component:

*app/javascript/App.vue*
```vue
<template>
  <div>
    <p class="text-2xl text-center font-bold mt-10">{{ message }}</p>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      message: "Welcome to Lioruby's template !"
    }
  }
}
</script>
```

Import this component:

*app/javascript/packs/application.js*
```javascript
import App from '../App.vue'
// ...
Vue.component('app', App)
```

And use it on yours rails views

*app/views/pages/home.html.erb*
```html
    <app></app>
```