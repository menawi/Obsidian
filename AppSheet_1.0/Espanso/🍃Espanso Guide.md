#espanso

[[Syntax]]


> Methods I found useful

## Prevent Accidents
### Use the "Word: True" method

```yaml
matches:

- trigger: '/google/'
  replace: 'test expander'
  word: true

➡️ Without word: true, any instance of '/google/' will expand into 'test expander'

_With_ word: true , only a solo '/google/' will expand into 'test expander'

```

## Multiline
### Use the ">" method

```yaml

- trigger: '/test-trig/'
  replace: > 
           test replacement text
           new line of that text 
           more lines
  word: true

# Having "word:true" is not neccessary BUT I like to keep it to prevent any mistakes from happening

```
