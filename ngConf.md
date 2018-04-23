# ngConf

## Router Stuff

- Nested router outlets
- Resolvers
  - have the router wait for an async operation before routing
  - can use data from the router instead of a service 
    - treats it as sync and gets rid of *ngIf
- can turn on a routing trace 
  - `enableTracing: true`
- Guarding routes
  - prevent routing to or from!
  - build a guard service
- lazy load feature modules
  - `loadChildren: "./path/to/module.module#className"`
- [code](https://github.com/deborah/MovieHunter-routing)

## Complex Forms Build Character

- [reactive forms](https://angular.io/guide/reactive-forms)
- auto save
  - publish-subscribe pattern
- Create custom classes for nested `FormGroups`
- [code](https://github.com/nscarlyon/dnd)


## Global Thermonuclear  Templates

- `npm install -g @angular-devkit/schematics-cli`
- `schematics blank <schematic-name>`
- Can write tests for schematics
- [code](https://github.com/brocco/global-thermonuclear-templates)

## Advanced DOM Stuff

- [code](ttps://github.com/maximusk/dom-manipulation-workshop)
- `git checkout tags/t1`
- Template references
- Presentation logic (in components)
  - Determines what to display
  - can reuse on other platforms
- Rendering logic (in directives)
  - maniplulates DOM
  - can share across application
- Renderer, use instead of call functions directly on element
- Angular works with View, not the DOM
  - `checkAndUpdateView` in `core.js`
- If the nodes are create by Angular (i.e. the template), you need to use Angular tools
  - (Not ture if you create things with jQuery, etc.)
- [View container](https://angular.io/api/core/ViewContainerRef)
  - Holds other views
  - Can create, destroy, and manipulate views
    - makes it safe to interact with DOM
  - [`ng-container`](https://angular.io/guide/structural-directives#ngcontainer)
  - [`ng-template`](https://angular.io/guide/structural-directives)
  - can have embedded and host views
    - There's a difference
  - You can preserve view created by factory or template to optimize
    - maybe a map of component names to views?

## "Containerizing" Angular with Docker

- Why Containers?
  - Simplifies building, shipping, and running apps
- What are Containers?
  - Image is a template
  - Container is taking the template creates the stuff
  - Dockerfile -> `docker build` -> Docker image
  - ```
    docker pull ngnix:alpine
    docker run -d -p 8080:80 nginx:alpine
    ```
  - -d: detached
  - `docker run -d -p <external port>:<internal port> <image name>`
- Running Angular on a "Real" Server
  - `-v $(pwd)/dist:/usr/share/nginx/html`
    - `<local directory>:<where we want it for the server>`
    - `ng build -dop false` prevents `dist` from getting deleted, just updates files
- Building Angular with Containers
- Angular and Services
  - Use Docker Compose
- Deploying Between Environments
  - push a docker image(s)

## Keynote Day 3

- Most of the time do lazy-loading and use service workers before doing SSR
- Use reactive forms


## Clean Code

- We spend 10 times for time reading code thn we do writing it
- How do we make code easier to read?
  - Style guide
  - If you don't understand it in 5 seconds, you should probably refactor it
  - Break things out into more functions
  - Generally, less than 20 lines per function
  - Remember that not everyone has the same context as you
  - Strings as constants when it fits
  - Avoid comments when
    - Explains "what"
    - Outdated and incorrect
    - Should've used a better name
  - Use comments
    - Explains "why"
    - Explains consequences
    - API Docs (jsdoc)
  - "Write dirty code, then clean it"

## Template Refs

  ```html
  <input #phone>
  <button (click)="click(phone.value)>
  ```

  ```html
  <app-hello #helloComp></app-hello>
  {{helloComp.name}}
  ```

  ```html
  <form #form="ngForm" >
  form is valid: {{form.valid}}
  form is dirty: {{form.dirty}}
  ```

## Build A Form Around It

- [code](https://stackblitz.com/@saniyusuf)
