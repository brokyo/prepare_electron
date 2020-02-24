
### Absolute_Truths_Described_Indirectly.md
> _These are some notes on_ [_Perpare_](http://prepare.awakening.systems)_: a [\[cybermystic\]](https://awakening.systems/) tool that helps the universe communicate through the “meaningful coincidence” created by the unknowability of interconnected systems._
> 
> _It combines light, color, sound, and AI-generated to help the user change reality through magic. Sit with it in a dark room [headphones recommended] and see if anything happens._
> 
> _Integrates with Philips Hue._

#### Cybermysticism
I like to build tools that combine the new age web aesthetic / “[rejected Western knowledge](https://en.wikipedia.org/wiki/Western_esotericism#Western_esotericism_as_%22rejected_knowledge%22)” with, like, weird computer stuff to see if the universe can communicate through code.

This one is called Prepare.

It was specifically inspired by _The Mysterium: Preparation for the Final Mystery_; a wild ass week-long performance by composer Alexander Scriabin that would close the door on the current incarnation of humanity and connect all things in the cosmos. It required the creation of a new language, excited all the senses, and was set in a temple that would crumble to nothing by the end of the performance, because of the performance. [It’s amazing](http://www.ernestjournal.co.uk/blog/2016/1/18/scriabin-the-mysterium).

Prepare gives the universe room to communicate through the “[meaningful coincidence](https://en.wikipedia.org/wiki/Synchronicity)” brought about by physical color, digital color, audio, and natural language generation. You’ll have to find those coincidences yourself but I've found the more you pay attention the more obvious they are. 

It only works if you believe in it.

c u on the other side,  
APC 🌒

#### Sound Explanation [[WebAudio](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API)] [[Tone.js](https://tonejs.github.io/)]

The music is created by four software synthesizers. Each synthesizer is given the sound of a chanting chorus [`cybermonks`) built [using the process I describe here](https://medium.com/@brokyo/in-excelsis-i-o-creating-digital-choirs-in-tone-js-f14d84982409).

A top-level system schedules eight random notes each with its own random attack, sustain, and release times. These notes regularly overlap to make cords that shift as other notes come in and out.

All synthesizers perform simultaneously and after all have finished their eight notes they start again with a low percentage chance of changing the vowel sound they’re singing or the key they’re in.

#### Color Explanation [[Philip Hue](https://www2.meethue.com/en-us)] [[p5.js](https://p5js.org/)]

Each note is synced with a change in color that gets more intense as the note's attack time passes and less intense the decay time passes.

Note-to-color correlation is based on Alexander Scriabin’s [_clavier à lumières_](https://en.wikipedia.org/wiki/Clavier_%C3%A0_lumi%C3%A8res)  which was one of his cosmic instruments and intended to trigger powerful things in the universe.

Physical color uses [node-hue-api](https://github.com/peter-murray/node-hue-api) to control the lights in a local environment while the browser uses P5 to mix the colors on the canvas.

Mixing colors on the web is hard but it’s important they match the room so I’m using [chroma.js](https://gka.github.io/chroma.js/) and doing the math in p5’s `draw` loop. This might be ridiculously computational intensive. I don’t know.

#### AI-Generated Text Explanation [[GPT-2](https://github.com/openai/gpt-2)] [[GPT-2 Simple](https://github.com/minimaxir/gpt-2-simple)]

The GPT-2 model was fine-tuned on the `cybermystic` canon including Theosophy books by [Alice Bailey](https://en.wikipedia.org/wiki/Alice_Bailey), Zen Koans, journal articles on theoretical physics, creation myths, Van Morrison lyrics, and lots and lots of internet new age PDFs and [blog posts](https://www.crystalinks.com/directory.html).

All the text was generated on GCP (as possible a place for the god of the wires as any) and the best text were picked and stored in a json file.

A handful of interesting starting phrases were picked to generate the text but the only manual editing was selecting the length. Everything else is directly from the machine.