# User Interface Design

**Colours:**

The main colour palette used for the typography is the Flexoki colour palette; it is an inky colour scheme that is designed for reading and writing on digital screens. As opposed to harsh whites on black or vice versa, the reduced contrast provides a more comfortable reading and viewing experience for the audience, preventing Halation. Additionally, since the documentary is astronomy-based, the background is kept solid black with stars, creating a cinematic void that allows the planets and facts to pop, emphasising their presence. The solid black background also creates uniformity across the entire presentation, making the transition between different planets feel like a single, continuous journey through space.

**Transition:**

Each planet is set to float in and out of each slide, taking the audience on a journey from one planet to another, further exemplifying the experience of travelling through space.

**Text and Visual Hierarchy**

To allow the audience to quickly catch the subject of the fact, a giant globe of the Earth is presented on screen, along with its alias “The Blue Planet” with the word “Blue” coloured in blue. In contrast to texts and description, the employment of implicit communication quickly establishes the subject and show that the Earth’s surface is mostly comprised of water, respecting the audience’s intelligence.

In addition, the main fact presented in this slide is that the Earth is a not perfect sphere due to how fast it is spinning. This fact is presented with the title “The Wobbly Life-Giver”. The use of

This title provides two key insights:
- “Wobbly” indicates that the Earth is spinning fast
- “Life-Giver” paints the Earth in a positive, home-like light

The word wobbly is highlighted in amber, providing a visual anchor and ensuring the audience’s eyes go immediately to the core subversion of the myth.

These texts are split into "Headline", "Fact", and "Description" with minimal words to avoid cognitive overload, allowing the audience to process both text and visual elements simultaneously.

To keep the volume of texts on the slide minimal, the impact of Earth’s rotation speed is presented with a rotating animation of the globe, allowing the audience to have an implicit understanding of the cause of Earth’s weird shape.  Finally, the Earth’s actual shape is also shown with an image as describing with words will only lose the attention and confuse the audience.

Finally, to avoid presenting information too quickly to the audience, the progressive disclosure technique is employed, whereby the image of an oblate sphere is only shown on click. By withdrawing showing the actual shape of the earth, it grows a sense of curiosity amongst the audience, keeping them engaged with the content.

**Animation and Audio**

The 3D model of the globe is set to spin 360° for the entirety of the slide along with a “whoosh” sound. These two elements are designed to synchronise, further exemplifying the speed at which the earth is spinning.

## Storyboard

**Headline:** Earth, The Blue Planet

**Fact Tagline:** The **Wobbly** Life-Giver

**Frame**

![[earth_storyboard.jpg]]

**Elements**

| Element | Description                   | Asset Source/Specs                                                           |
| ------- | ----------------------------- | ---------------------------------------------------------------------------- |
| E       | 3D model of the Earth         | Stock 3D model in PowerPoint                                                 |
| T1      | Headline of the slide         | Font: Inter<br>Size: 80<br>Colour: <br>- White: \#CECDC3<br>- Blue: \#4385BE |
| T2      | Main fact of the slide        | Font: Inter<br>Size: 54<br>Colour:<br>- White: \#CECDC3<br>- Amber: \#CB6120 |
| T3      | Short description of the fact | Font: Arial<br>Size: 32<br>Colour: <br>- White: \#CECDC3                     |
| OS      | An image of an oblate sphere  | Oblate Sphere PNG                                                            |
| Audio   | "Whoosh" sound                | File: `.wav` or `.mp3`                                                       |

**Technical Specifications**

| Phase       | Technical Action |                                                       | Purpose                                                     |
| ----------- | ---------------- | ----------------------------------------------------- | ----------------------------------------------------------- |
|             | Element          | Action                                                |                                                             |
| Entrance    | E                | 1.50s Glide Transition                                | To simulate travelling to Earth                             |
|             | T1               | 0.50s Fly In Transition                               | To keep the content dynamic                                 |
|             | T2               | 0.50s Fly In Transition<br><br>1.0s Teeter Transition | Wobble to emphasise earth’s imperfect shape                 |
|             | T3               | 0.50s Fly In Transition                               | Accompany the fact in the slide                             |
| Trigger 1   | OS               | Glides into the slide on click                        | Withdraw information until the right moment                 |
| Persistence | E                | **Loop Spin:** "Until End of Slide"                   | Maintains the "Live" feel of the planet during presentation |
| Audio Sync  | -                | 0.25s Delay on "Whoosh"                               | Creates an "Acceleration Effect" rather than a sudden jolt. |

**Speaker Script**

The Earth is actually...