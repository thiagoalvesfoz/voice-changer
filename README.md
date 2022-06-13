# VOICE CHANGER

apply voice effects

# NOTE:

- Effects require an Audio Buffer type and return an AudioBuffer promise

### How to use

```javascript
async function application() {
  let blobAudio; // <- your blob audio here

  async function applyEffects(blob) {
    let audioCtx = new AudioContext();
    const arrayBuffer = await new Response(blob).arrayBuffer();
    const audioBuffer = await audioCtx.decodeAudioData(arrayBuffer);
    return await effects.bigfone(audioBuffer);
  }

  const audioBuffer = await applyEffects(blobAudio);

  // some AudioBuffer-Blob converter here
  const blob = audioBufferToBlobAudio(audioBuffer); // omitted code
}
```

## License

MIT, see [LICENSE.md](http://github.com/thiagoalvesfoz/validate-wav-from-buffer/LICENSE.md) for details.
