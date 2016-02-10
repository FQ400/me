title: Asset Pipeline - Modern Frontend Development
author:
  name: Carsten Lamm
  github: https://github.com/FQ400
  url: http://www.kontextr.com
output: basic.html
--

# Asset Pipeline
## Modern Frontend Development
## by Carsten Lamm

--

### table of content

1. Background _(1)_  
1. Frontend Definition _(1)_  
1. Asset Pipeline? _(1)_  
1. Tools _(3)_  
1. Types _(1)_  
1. Basic Setup _(1)_  
1. Extended Setup _(2)_  
1. Done _(1)_  
1. Sources _(1)_  

--

### My Background

- started with Rails 2 up to Rails 3 (~3 years)
- **S**ingle **P**age **A**pplications using REST-APIs
  - AngularJS (~2 year)
- node and React (~1 year)
- now back to Rails 4

--

### Frontend Development means ...

... building web applications with UI  
... for mobile/desktop devices with/without touch  
... with different screen resolutions.

... also use build tools to optimize performance.  

... automatically test your code and layouts.  

... tracking and AB-Tests.  
...

--

### Asset Pipeline ...

... is a mighty building tool  
... which combines and compresses assets.  

... super integrated into Rails via gem.  

... produces assets marked with hashes.  

... provides the easiest way to invoke multiple parser.  
`   => application.css.scss.erb`  

--

### some Tools

[node](https://nodejs.org/en/) - Javascript on the server  
[npm](https://www.npmjs.com/) - Node Package Manager including package.json  
[grunt](http://gruntjs.com/) - Asset build tool - JSON based  
[gulp](https://github.com/gulpjs/gulp/blob/master/docs/getting-started.md) - Asset build tool - stream based  
[bower](http://bower.io/) - Package Manager for Javascript & CSS libs  
[webpack](https://webpack.github.io/) - Asset build tool - works fine with babel/ES2015  
[EcmaScript 2015](https://github.com/lukehoban/es6features) - latest Javascript, needs to be transpiled (source-to-source)  
[babel](https://babeljs.io/) - Javascript compiler for ES2015  
[bundler](http://bundler.io/) - Ruby Package Manager  
[Asset Pipeline](http://guides.rubyonrails.org/asset_pipeline.html) - Asset build tool - sprockets based  

--

### grouped tools

![](./grouped_tools.jpg)

--

## Confusion by google: rails + ______

- rails webpack
- rails gulp
- rails ES6

--

### kind of web app

- API/multiple clients - SPA
- (no) API/one client
- enterprise app / small website
- progressive enhancement vs graceful degradation

--

### Basic Setup

- bundler for ruby dependencies
- (bower for CSS/JS dependencies) => [rails-assets.org](rails-assets.org)

**Gemfile**  
`source 'https://rails-assets.org'`  
`gem 'rails-assets-lodash'`  

**Assets**  
`//= lodash`  
`//= require_tree .`

--

### extended setup ES2015 / ES6

**npm >= v3**  
`npm install babel-preset-es2015 --save-dev`

**.babelrc**  
`{ "presets": ["es2015"] }`

**Gemfile**  
`gem sprockets-es6`

**initializer/es6.rb**  
`require "sprockets/es6"`

--

### Done - can be used

- all files like `*.js.es6` are found
- can be access via `//= require class_es6` directive

**open point**
- es2015 for inline scripts
- es2015 modules
  - defined but not implemented

--
### Sources

[Wiki Compiler](https://en.wikipedia.org/wiki/Source-to-source_compiler)  
[Standard ECMA-262 6th Edition / June 2015](http://www.ecma-international.org/ecma-262/6.0/)  
[Cleaver](https://www.npmjs.com/package/cleaver)  
[Sprockets](https://github.com/rails/sprockets)  
[Progressive Enhancement](https://en.wikipedia.org/wiki/Progressive_enhancement)  
[Graceful Degradation](https://en.wikipedia.org/wiki/Fault_tolerance)  
[Babel Rails](https://babeljs.io/docs/setup/#rails)
