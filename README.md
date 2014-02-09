meteor-accounts-ui-bootstrap-3
=====================================

Meteor accounts-ui styled with twitter/bootstrap 3 and internationalization

Prerequisites
-------------

Use the meteorite package manager
http://oortcloud.github.com/meteorite/

[sudo] npm install -g meteorite

How to add to your meteor app
-----------------------------

mrt add accounts-ui-bootstrap-3
mrt add just-i18n

How to use
-------------

Add {{ loginButtons }} to your template

Aligning
-------------

You can align loginButtons dropdown with `align` parameter. Without parameter it defaults to `align="right"`.

```
{{ loginButtons align="right"}}
```
or
```
{{ loginButtons align="left"}}
```

Example:

```html
<div class="navbar navbar-default" role="navigation">
  <div class="navbar-header">
    <a class="navbar-brand" href="#">Project name</a>
  </div>
  <div class="navbar-collapse collapse">
    <ul class="nav navbar-nav">
      <li class="active"><a href="#">Link</a></li>
    </ul>
    <ul class="nav navbar-nav navbar-right">
      {{ loginButtons }} <!-- here -->
    </ul>
  </div>
</div>
```

Add additional logged in actions
--------------------------------

You can add additional markup to the logged in dropdown, e.g. to edit
the user's account or profile, by defining a 
`_loginButtonsAdditionalLoggedInDropdownActions` template and specifying
the corresponding events.

```html
<template name="_loginButtonsAdditionalLoggedInDropdownActions">
  <button class="btn btn-default btn-block" id="login-buttons-edit-profile">Edit profile</button>
</template>
```

```javascript
Template._loginButtonsLoggedInDropdown.events({
  'click #login-buttons-edit-profile': function(event) {
    event.stopPropagation();
    Template._loginButtons.toggleDropdown();
    Router.go('profileEdit');
  }
});
```


Screenshots
-------------

![Sign In](https://dl.dropboxusercontent.com/u/7263172/1.png)
![Sign Up](https://dl.dropboxusercontent.com/u/7263172/2.png)
![Configure Login Service](https://dl.dropboxusercontent.com/u/7263172/3.png)
