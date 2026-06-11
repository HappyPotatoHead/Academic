# User Interface Design

**Text and Visual Hierarchy**

The alias used in this slide is "The Rusty Desert", with "Rusty" coloured in orange. Employing implicit communication again, the audience is able to visualise a dry, red surface of the Mars without textual description. The company of an image of Mars also further facilitate this imagery. 

The main fact presented in this slide is the presence of the largest canyon ever recorded in our solar system. This fact is presented with "Home to Valles Marineris", whereby "Valles Marineris" is red in colour to draw the attention of the audience towards the fact. The use of red for the canyon's name creates a thematic link to the rust coloured surface of the planet, creating a semantic cue to reinforce the subject matter. To further illustrate the size of the canyon, the word "largest" is also scaled up and coloured red. 

Similarly, the texts are split into "Headline", "Fact", and "Description" with minimal words to provide room for personal interpretation while avoiding cognitive overload.

This fact is presented in two slides; the first slide prepares the audience while the second slide provides a visualisation on the appearance of the canyon. To avoid breaking the immersion, the transition from the first slide to the second slide is made to mimic a zooming effect. The transition utilises progressive disclosure via a morph zoom, maintaining spatial continuity so the audience understands where the canyon is located on the planetary sphere. 

Additionally, since the large scales are often difficult to grasp, an animation of an icon of a person walking through the entire canyon is played as the presenter presents. By using a human walking icon as a relatable unit of measurement, the design translates an abstract astronomical distance into a 'Biological Effort' that the audience can intuitively process.

# Story board

**Headline:** Mars, The Rusty Desert

**Fact Tagline:** The **Wobbly** Life-Giver

**Frame**

![[mars_introduction.png]]

![[canyon.png]]

**Elements**

| Slide No. | Element | Description                   | Asset Source/Specs                                                             |
| --------- | ------- | ----------------------------- | ------------------------------------------------------------------------------ |
| 1         | M       | An image of Mars              | NASA photo of Mars                                                             |
|           | T1      | Headline of the slide         | Font: Inter<br>Size: 80<br>Colour: <br>- White: \#CECDC3<br>- Orange: \#DA702C |
|           | T2      | Main fact of the slide        | Font: Inter<br>Size: 66<br>Colour:<br>- White: \#CECDC3<br>- Red: \#D14D41     |
|           | T3      | Short description of the fact | Font: Arial<br>Size: 32<br>Colour: <br>- White: \#CECDC3<br>- Red: \#D14D41    |
| 2         | M       | An image of Mars              | NASA photo of Mars                                                             |
|           | >       | Emphasis on the canyon        | NASA photo of the canyon                                                       |
|           | I       | Icon of a person              | Stock icon in PowerPoint                                                       |

**Technical specifications**

| Slide No. | Phase     | Technical Action |                                | Purpose                                          |
| --------- | --------- | ---------------- | ------------------------------ | ------------------------------------------------ |
|           |           | Element          | Action                         |                                                  |
| Slide 1   | Entrance  | M                | 1.50s Glide Transition         | To simulate travelling to Mars                   |
|           |           | T1               | 0.50s Fly In Transition        | To keep the content dynamic                      |
|           |           | T2               | 0.50s Fly In Transition        |                                                  |
|           |           | T3               | 0.50s Fly In Transition        |                                                  |
|           | Trigger 1 | T3               | Glides into the slide on click | Withdraw information until the right moment      |
| Slide 2   | Entrance  | M                | 2.00s Morph Transition         | Provide a "zoom in" effect.                      |
|           | Trigger 1 | I                | 2.00s Custom Path animation    | To simulate traversing the entire canyon by foot |




