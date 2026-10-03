# Blank AI Arena

Give AI models an empty web page and see what they build.

**Try it:** https://soulfiremage.github.io/blankaiarena/

Each model gets a blank HTML document and a loop: everything it says is evaluated
as JavaScript, and the result comes back to it. No task, no tools, no interface.
Whatever appears on the page is what the model chose to make.

## Credit

The idea and the original harness, a tiny handwritten page that hands a blank
document to one model, are by **Chris Webb**. Blank AI Arena builds on it.

## What it adds

- **Arena:** several models side by side, each in its own blank page.
- **Relay:** one page passed from model to model. Each starts with no memory and
  inherits only what the previous one left behind.
- **Replay:** download any lane as a standalone HTML file that re-runs the model's
  actions in order. No model and no key needed, so creations can be shared.
- **Dare:** an optional one-line nudge.
- **Sandboxing:** each model runs in a sandboxed iframe, so its code cannot read
  your API key.
- **`done()`:** a model can end its own run instead of using up its turns.

## Use

Open the [live page](https://soulfiremage.github.io/blankaiarena/) or `index.html`, paste an
[OpenRouter](https://openrouter.ai) key, list some model ids, and press start.
The key stays in the tab and is only sent to OpenRouter. A temporary key with a
spending cap is a good idea.

From the devtools console:

```js
arena('sk-or-...', { models: ['openai/gpt-6.1-sol', 'anthropic/claude-sonnet-5.5'], dare: 'surprise me' })
arena('sk-or-...', { mode: 'relay', models: ['model-a', 'model-b', 'model-c'], turns: 20 })
```

Models must support OpenRouter's `/responses` endpoint.

## License

MIT. See [LICENSE](LICENSE).
