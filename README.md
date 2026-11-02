# Gift Page Templates

Three single-file HTML gift pages. No build step, no dependencies, no framework. Open in a browser, edit the `CONFIG` block at the top of the file, host it anywhere.

Built for people who want to send a link instead of a card — and for developers who need a starting point instead of a design.

| Template | What it does | File |
|---|---|---|
| **Heart burst** | Tap a heart 7 times. On the last tap it bursts into particles and reveals a letter with photos. | `heart-burst.html` |
| **Star sky** | A night sky where each star hides a memory. Reveal all of them for an ending message. | `star-sky.html` |
| **Countdown** | Counts down to a date, then unlocks a hidden message. | `countdown.html` |

## Use

```bash
git clone https://github.com/sostenesapollo/gift-page-templates
cd gift-page-templates
open heart-burst.html
```

Edit the `CONFIG` object at the top of the `<script>` in the file you chose:

```js
const CONFIG = {
  taps: 7,
  title: "I couldn't wrap this one",
  message: "Every year I buy something and it's fine...",
  signature: "— happy birthday",
  photos: ["https://example.com/photo-1.jpg"]
};
```

Deploy: drag the folder into Netlify Drop, `npx vercel`, or push to GitHub Pages. It's static HTML — anything works.

## Details worth knowing

- **Mobile first.** Every template is designed at 390px wide and scales up.
- **No tracking, no network calls.** The only requests are the image URLs you supply.
- **Respects `prefers-reduced-motion`.** Animations are disabled for users who ask for it.
- **Escapes user text.** The `message` field is HTML-escaped before render, so an apostrophe or `<` doesn't break the page.
- **Vibration and canvas particles are optional.** Both degrade silently where unsupported.
- **No localStorage, no cookies.** Nothing persists between visits.

## Customizing

Colors live in `:root` at the top of each file:

```css
:root{
  --bg:#0b0410;
  --accent:#ff2e6d;
  --soft:#b98fd6;
}
```

The countdown accepts any ISO 8601 string with an offset, so it stays correct across timezones:

```js
target: "2026-12-25T00:00:00-03:00"
```

## Browser support

Chrome, Safari, Firefox, Edge — last two versions. Uses `backdrop-filter`, `aspect-ratio`, and CSS custom properties. Safari needs `-webkit-backdrop-filter` only on versions before 18; the letter still renders without the blur.

## License

MIT. Use commercially, remix, resell, no attribution required.

---

### Want this without writing code?

These templates are open source versions of a few pages from [Gifts QR](https://giftsqr.com) — there they come with a form, a photo uploader, a QR code and a link, so you can create one in about three minutes without touching HTML.

34 templates: birthday matrix, voice wall, time capsule, scratch card, virtual mixtape, fortune cookies, and the three above.
