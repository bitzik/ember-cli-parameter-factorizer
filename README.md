# Ember-cli-setting-factorizer

This addon is an attempt to introduce a nice way to avoid component invocation that are 3 or 4 lines long.
The basic idea is to seamlessly allow to use a `setting` parameter to gather all the other one on a component or to bind them one by one.

## The idea

When developing with Ember.js I often find myself having components nested within components themselves nested within components...
I was unfortunately unable to find a nice solution to allow to change some of the deeply embedded from the outmost template.

So I often end up with a `something.hbs` that looks like that:

    {{some-feature-full-component
        directParameter=model.something
        oneLevelDeepComponentOptionalClass= "something-class",
        ...
        ...
        //Picture 5 or 6 parameters here
    }}

Most of time, these nested parameters are merely cosmetic stuff... So what if we could define in `something.js` a parameter object like this:

    parameters: {

    }
