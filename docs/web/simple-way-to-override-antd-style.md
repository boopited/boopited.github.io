---
layout: post
title: Override ant design theme
parent: Web UI
nav_order: 1
date: 2019-12-26
---

# Simple way to override theme of ant design

## Foreword

Referring to [ant.design](https://ant.design/docs/react/customize-theme-cn)

Convert customized base style from less to css, and import css in index.js, period.

Pros:

1. less support is not necessary.
2. Easy to customize any component styles in your project once for all.

Cons:

You may have to regenerate your theme css when you change your base style.

## Now let's begin

#### 1. Get lessc

'lessc' is needed, or install it.

`npm install less -g`(better for later use)

or

`npm install less`

#### 2. Define base style

Create your base style in 'less', something like this:

```
@import "./antd.less";   // Import Ant Design styles by less entry

@primary-color: #d228e9;                         // primary color for all components
@link-color: #1890ff;                            // link color
@success-color: #52c41a;                         // success state color
@warning-color: #faad14;                         // warning state color
@error-color: #f5222d;                           // error state color
@font-size-base: 40px;                           // major text font size
@heading-color: rgba(0, 0, 0, .85);              // heading text color
@text-color: rgba(0, 0, 0, .65);                 // major text color
@text-color-secondary : rgba(0, 0, 0, .45);      // secondary text color
@disabled-color : rgba(0, 0, 0, .25);            // disable state color
@border-radius-base: 4px;                        // major border radius
@border-color-base: #d9d9d9;                     // major border color
@box-shadow-base: 0 2px 8px rgba(0, 0, 0, .15);  // major shadow for layers
```

'antd.less' could be found in './node_modules/antd/dist'.

#### 3. Convert less to css

`lessc --js custom-style.less custom-style.css`

'lessc' is available if less was installed global.

Or check './node_modules/less/bin/'

#### 4. Import css in index.js

Copy 'custom-style.css' to your src folder, and import it in index.js.

Then you can use this customized style in your project.

