# Ember Components Diagnostic
Record your responses inside the fenced code blocks below each question.

1.  Give an example of a visual hierarchy that could be modeled with components. Explain why each piece might be it's own component.

    ```md
    A list of lists would be modeled with components. This would consist of the
    high level list of lists: 'listr-list' then the sub lists 'cards' and the
    'items' in those sub lists. These would need to be their own components as
    delete buttons need to be placed in 'items', create buttons need to be placed
    in 'cards', etc...
    ```

1.  What is the command to generate a new component called '`my-map`'?

    ```sh
    ember g component my-map
    ```

1.  What files are created and/or edited to produce a component, and what are their responsibilities?

    ```md
    created files:
    - component.js -> for defining the actions that are called in the component
                      and sending the actions up to the next level accordingly.
    - template.hbs -> for definging how the component is rendered in the browser
                      and placing things like buttons.
    - component-test.js -> for running tests the new component

    ```

1.  Suppose you have a component '`my-contact`', which is loaded from
    '`app/contacts/template.hbs`' when visiting the `/contacts` route. What is
    the syntax (code that is written) to render this component inside that template?

    ```html
    {{#each model as |contact|}}
      {{my-contact contact=contact}}
    {{/each}}
    ```

1.  Each contact has multiple phone numbers. Suppose you also have '`my-phone`'
    nested under '`my-contact`'. What is the code you would write in
    '`app/components/my-contact/template.hbs`' to load the nested component and
    pass it data?

    ```html
    {{#each model as |phone|}}
      {{my-contact/my-phone phone=phone}}
    {{/each}}
    ```
