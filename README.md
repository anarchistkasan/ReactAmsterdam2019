Talks - general thread available here- https://www.youtube.com/watch?v=smBND2pwdUE (per talks videos are about to be published)

----------------
Kent C. Dodds (Trainer, USA) Requisite React
----------------

The talk was generally more a motivational one to inspire people learning the fundamentals

General notes:

    - the better u understand abstraction - the better u use it

    - custom components are just references to variables

    - use composite components (compound components - React.cloneElement) only when needed


Key take-aways:
— learn fundamentals
— understand abstractions
— dive into node_modules


In general, I would not recommend this talk

----------------
Siddharth Kshetrapal (Independent Developer, India) Refactoring React
----------------

this talk was more useful with typical examples you should pay attention to detect the code smell

Things to pay attention to:

    - props inside state — code smell

    -interaction event handling - onClick - code smell (no accessibility support) - should be onChange

        - not interaction but behavior - onToggle

        - name behavior not interaction

       - onChange vs onToggle to minimize number of strings to learn (onChange is more common)

    - one component too interested in child components - further reading - Optimized for change (Dan Abramov)

        - when surroundings change - component should  not change (unit test should not fail)

    {…props} - code smell

        eg, inline style will be overridem as order matters then

        order of props is important

        {`form ${className}`}

    mix control and uncontrolled components

    login form shouldn not care of ux (Single responsibility)

        no disabling button on input change

        HOC to with props, accepting Component and handling change event

        class component turns to functional with this

    tests use getByText instead of selectors

    single prop  but no children - code smell

        prop.message - is a child (don’t create a prop, unless you need it) vs <Component><span>Message</span></Component>

    don’t copy-paste disabled prop, but assign disabled to all children in a loop React.Children

    React.clone - code smell

        use context instead (<> wrapper will not make accessible grandchildren)

        use only if the owner need to know everything about children ( if just a prop - don't use React.context)

        if private - use Context



https://sid.studio/refactoring/


----------------
Andrey Okonetchnikov (Freelance, Austria) A Common Design Language. Let Designers and Developers talk to each other
----------------


The talk was more about argumentations on why you need design system and what benefits it gives you.


Notes:

    "you don't need to uglify your code, it's already ugly”
    User Interface = language
    UI Promitives in between UX and dev

----------------
Mark Dalgleish (Seek, Australia) Designing with React
----------------

The talk introduced a pretty cool tool - https://github.com/seek-oss/playroom

Notes:

    components => dsl
    React sketch.app
    html-sketchapp
    modulzstudio, framex, interplay

Runkit + npm - trying npm package

Playroom
npm install playroom
https://github.com/seek-oss/playroom

----------------
Lightening talks:
----------------

----
next.js
----

high load on production
> 15000 apps are using next.js

https://mdxjs.com/

----
fast ssr react
----

Crystallize.com

Uncanny valley

Looks interactive, eh = LIE (loaders)

netflix - react only on server

----
speeding up ssr with ESX
----


https://github.com/esxjs/esx


demystifying server-render React

ssr - good seo
0.2% users have disabled JS (2.7% - in some countries)

TTFB - time to first byte is slower with ssr

----------------
Max Stoiber (GitHub, Austria) Tech Regrets at Spectrum
----------------

Practical advice on what exactly did went wrong and what theyt learned at Spectrum

     not using react-native-web
        one code for reactNative and website
        mobile first
        optimize for speed and flexibility - all about experimentation and momentum
    not using Next.js

        ssr

        use existing solutions, particular;y when u don’t understand problem

    Using RethinkDB

        realtime

        chase fits

        little knowledge of running it in prod

        > 50 chasefits - no support

        carefully choose core technologies, that are hard to change
        => when selcting tools-  prioritize community size and active maintance

     Using DraftJs and WYSIWYG -editor

        month - building an editor and it was extremely buggy

     be carefull with cutting edge technologies

    be open with roadmap (listen to user feedback)

----------------
Max Gallo (DAZN, UK) Scaling Applications with Microfrontends
----------------

Nice well structured talk - recommended

    Why MicroFrontends

    What is a mcfr

    how they work

    Why

Database > monolith backend > SPA

if more users? - scaling monolith backend
-> load balancers, multiple teams working on release
-> microservices, api gateways

Frontend was not changed - same codebase for all teams
 -> communication overhead for code and implementations
 -> Infrastructure, microservices are autonomous

how much small should a component be?

    one business domain - one team

    autonomy -> responsibility -> innovation

    What is?

copy-paste code
learn from others -Open components(OpenTable) > Interface framewors- Mozaic , fragments - pieces of pages owned by different teams(Zalando) -> Iframes & event bus(Spotify) - C++ +Iframe- event bus, spotlets. changed the architecture just for web

DAZN

    independ implementation, no sharing logic - enable team to work independ

    per business domain

    owned by a single team

1 app - 1 domain
authentication - Landing pages - customer support - my account - discovery and playback

Autonomous spa
one microfrontend per time
one team, one subdomain, one microfrontend

in practice = html+js+css

    under the hood


microfrontends — Boostrap (loader) - User

Bootstrap - html+js
    download immediately - just a spinning log (500ms) - load microfrontend

    app startup

    client side routing

    provides lifecycle API for microfrontends communications

    i/o operations- device api abstractions (30 different devices)

Shared components

  !  how to keep consistency in UI

    we don't (copy-paste)

    code duplication vs Team autonomy- reduce Cross team comms, Dev team growth, not repetitive UI

Deploy

all stored next to each other - completely separate

Challenges of scaling

    scaling the teams, people

    reducing communication overhead

    innovate

----------------
Elizabet Oliveira (Optum, Ireland) An SVG’s Tale
----------------

the talks was nicely presented, with the story on how to use svg with react

    svg as React.component

    transform svg into JSX


React kawaii project


Interesting was the moment when the speaker started to play hip-hop on the stage


----------------
Peggy Rayzis (Apollo, USA) The GraphQL developer experience
----------------

The talk about the basics of GraphQl and motivation behind it.

good DX

    nonobtrusive

    predictable

    instant feedback loop

    solve problems

Data layer:

     shape of data
    errors state and loading
    how to cache

Before - trying to make event emitter to behave like a cache

=> don’t  put all your state to cache


----------------
Ashi Krishnan (GitHub, UK) Painting Pixels with WebGL with React Hooks
----------------

The talks was about presenting the way to work with WebGl in web, with some React smell

Notes:

@rakshesha

Vertex Shader - OpenGL
position-force-color - 3 args

Luma libraty for opengl


react transitioning between scenes. inside scene - no react

reconcile on each frame change

react +request animation frame - no way

data flows only one way

spreadsheet

game of life with stylus touch



