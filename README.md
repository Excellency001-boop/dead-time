# DEAD TIME

**A void that only moves while an AI is thinking. In the wait, you gather light into one object and carry it back into reality when the answer returns.**

Built solo for the Commonsmade hackathon. Theme: *humans spend 30 million hours a day waiting on AI. Make waiting for AI fun.*

---

## The problem, said plainly

Every day, all of us together lose 30 million hours staring at a spinner. That time is not empty. Real machines are burning real compute on our behalf in that gap. We just never get to see it, feel it, or keep any of it.

Dead Time takes that gap and makes it a place.

## The idea in one sentence

You type a thought and release it into the dark. The moment the model starts thinking, a black void ignites and time turns on. While you wait, you gather drifting filaments of light into one object with your hands. The instant the answer comes back, the whole world freezes cold and your object locks into a crystal. Then you pull it out of the void and keep it.

Wait. Make. Keep. That is the whole loop, and you feel all of it inside the first sixty seconds.

## The one law that makes this real

Almost everything in a hackathon is a beautiful animation on a timer. Dead Time is not.

There is a single variable called `energy`. It is fed by exactly one thing: a real token arriving from a real model, streamed to the browser one token at a time. A second variable, `voidTime`, is the clock that every shader, every filament, and every sound reads from. It only advances when `energy` is above zero.

So the coupling is literal, not decorative:

> The world moves if and only if real tokens are arriving.

Stop the model and the universe stops with it. There is no idle loop, no fake breathing, no timer faking the middle. You can read it in the code in ten seconds: `energy` is raised in one function, `onToken()`, called from one place, a token landing in the stream. Every frame only ever drains it.

That is the thing no other entry can copy without meaning it. A judge who realizes "this only moves while my model is thinking" is a judge who remembers Dead Time.

## Why this is the Commons thesis, not just an art piece

Commons is building an economy where attention and compute become value that moves. Dead Time is a working, felt demonstration of that exact idea, from the inside.

- **Attention becomes substance.** Your wait is not dead time anymore. It is the raw material. The longer and denser the inference, the richer the object you can make. Attention paid during real compute is the thing you spend.
- **Compute becomes something you can hold.** The object is a receipt of real inference. It is minted from the tokens the machine actually produced. It carries how long you waited and how hard the model worked, baked into its shape and its seed.
- **Value that survives.** When you carry an object out, it persists. It sits on your reality shelf across sessions, a growing collection of the waits you kept. This is the seed of Build2Earn: the wait produced a thing, the thing is yours, and it is durable.
- **The rail is ready.** Each carried object is a discrete, ownable, verifiable artifact tied to a real compute event. That is precisely the shape you settle over x402 / USDC or account for in compute credits. The build does not charge money (see honesty note below), but it produces exactly the object the Commons rail is designed to move.

Dead Time does not talk about the waiting economy. It lets you stand inside one for sixty seconds.

## What you actually feel (the loop)

1. **Enter.** Pure black. One line: *type a thought, then release it into the dark.* Your letters appear as light. No buttons, no chrome.
2. **Ignite.** You release. The first real token hits and the void flares to life. Time turns on. You hear it turn on.
3. **Gather.** Filaments of light drift out of the fog. You hold and pull them together with your cursor, shaping where the light collects. A contracting ring shows the pull. The object grows with every token.
4. **Freeze.** The answer returns. A shockwave rings outward, the fog drains to black and cold, and your gathered light snaps into a crystalline lattice. Silence. This is the dangerous, expensive beat.
5. **Carry out.** One gesture pulls the crystal up and out of the void into reality. It joins your shelf, a small constellation you can hover, and reopen later.

## Honesty note (what is real, what is staged)

I would rather tell you than have you find it.

- **Real:** the honest clock, the live token stream from a local model, the ignition, the gather, the freeze, the crystallization, the carry-out, and the persistent shelf. All of it is wired to actual inference.
- **Staged for now:** money settlement. The economic layer above is the design intent and the object is built to plug straight into it, but this build takes no card and moves no funds, on purpose (see below). The value it produces is real and ownable. The rail on top is the next step, not a claim about today.
- **Demo mode:** add `?demo=1` for a clearly labelled *simulated wait*, so the piece can be shown to someone without a local model running. It is never presented as real inference.

## Constraints I held myself to

- **No card, no paid service, ever.** It runs on a local model through Ollama. Zero cost, no billing page, works offline.
- **Nothing that needs my laptop babysat.** Short on-demand runs. The world is even supposed to sleep when the machine sleeps. That is on theme.
- **One file, no build step.** Vanilla WebGL and Canvas2D and Web Audio, all synthesized, nothing external to fetch. It just opens and works.

## Design language

Dark first. Volumetric fog. Almost no traditional interface. Sound is a primary material, not decoration: a sub-bass drone that breathes with the token cadence, a thinking pad, per-token grains, an ignition swell, a freeze ring. Cinematic grade on top: bloom, film grain that freezes when time freezes, a vignette, and a cold frost that drains the world when inference stops.

The feeling, stated once and defended everywhere: power and play, wrapped in awe and dread, paying out into danger and reward.

## Run it

Two terminals.

```bash
OLLAMA_ORIGINS=* ollama serve
```

```bash
cd dead-time/app && python3 -m http.server 8080
```

Then open **http://localhost:8080/**, click once, type a thought, and press Enter.

- First time only: `ollama pull llama3.2:1b`
- Pick a different model: `?model=llama3.2:3b`
- Show it without a local model: `?demo=1`
- Toggle the honest-clock readout: the backtick key `` ` ``

The small readout along the bottom (`state / tokens / tok/s / energy`) is there on purpose. It is the proof that the clock is real. Watch it die when the answer lands.

## The demo, in five shots

1. Black screen. Type a real question. Hold on the stillness for two seconds.
2. Release. The ignition. Let them see time turn on.
3. Gather light for a few seconds. Show the object forming from the wait.
4. **The money shot:** the answer returns, the freeze hits, the world goes cold and silent. Do not cut away. Let the silence sit.
5. Carry the crystal out to the shelf. End on the shelf filling with kept waits.

If the freeze beat lands, you have already won the room.
