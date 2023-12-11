Initial draft of intro section

# Introduction

In this course, we are going to use Python as a tool to take on the concept of good data visualisation.  In addition to walking you through some step-by-step advice regarding libraries that are available, and building plot templates that let you save out your figures to high resolution pngs or pdf files, we are also going to disucss how best to represent your data in a way that is meaningful, asthetically pleasing, and scientifically robust.

Before we even get into the libraries and modules that are available, or the actual step-by-step of how to use these tools to build a plot, we are going to walk through some of the important considerations when deciding how you are going to visualise your data.

Choosing the type of plot to use to represent your data is not something obvious or straightforward, and is something tht will never have a unique solution: there are lots of good options that may win out in certain situations.

In order to structure this discussion a little better, we are going to use the PLOS Computational Biology paper _Ten Simple Rules for Better Figures_ by [Rougier, Droettboom and Bourne, 2014](https://doi.org/10.1371/journal.pcbi.1003833).

## Ten Simple Rules for Better Figures

Rougier et al. (2014) state that scientific visualisation&mdash;the process of graphically displaying scientific data&mdash;is a process that is neither direct nor automatic, and acts as a graphical interface between people and data. They provide ten rules as a guideline to consider whenever you are creating a scientific figure.

### Rule 1: Know Your Audience

One of the key factors to consider when designing a figure is to consider who will be reading it.

- Is the figure for yourself or direct collaborators? This may be the case if you are quickly checking if resuolts are expected, are pulling together some notes for a supervisory or team meeting, or have some questions for a collaborator about some recent results.
- Is the figure for a scientific publication and so for a broader audience who has technical knowledge but does not know the details of your work specifically?
- Are you presenting a talk or a poster at a conference where the audience are mainly experts in your niche field?
- Is your audience going to be undergraduate students where the aim is to convey a concept or method with your data as an example, instead of conveying your results specifically?
- Is you data visualisation being used in an outreach setting for the general public without any assumed research or field-specific knowledge?

Challenge: For each of the suggested audiences above, discuss different requirements for data visualisation.

(Turn below into drop-down)

- When creating quick plots for yourself or direct collaborators, you can probably cut more corners than you normally would, as you already understand your subject area and analysis. However, don't underestimate how much you can forget in a few short months: making sure your plots are easily readible, with sensible axes labels and titles, will help future you to remember what exactly it is you were tyring to do!
- When producing a figure for a scientific publication, you need to ensure you haven't cut any corners, and that all relevant information needed is available for a broader audience to be able to digest your work. Figures in a publication can get away with being a bit more dense as usually the reader spends a bit longer looking at them than the equivalent audience member at a presentation or poster session.
- At a conference, the audience may range from quite broad to very niche. In general, conference delegates will have less time to absorb your visualisation than someone reading a scientific article would, so in general they need to be less information-dense. Additionally, you can support the physical figure with description and explanation during the presentation, and so the design can be a little more minimal and less self-contained.
- When presenting in a teaching setting, often times it is a concept, analysis method, relationship between variables etc. that is being taught, as opposed to presenting results as in a manuscript or at a conference. Additional labels, detailed and clear labels and legends, and reduced datasets can help make these style of visualisations more digestible.
- Figures for the general public are often the most difficult to desgin, and should only contain the most essential details of your work. Avoid non-standard chart types, and potentially lean into the possibility of schematics and summary plots.

### Rule 2: Identify Your Message

A figure can express an idea quickly, succinctly, and much more straightforwardly than text can: the old adage "a picture tells a thousand words" is true! However, it is important to know exactly what the message of the figure is, to avoid creating either pointless plots that don't really tell much, or overly complex plots that try to tell far too much.

In the same way that you need to decide on the key message for any research paper, and then in more granular detail pick the key message of each subsection of your results, before you start plotting or pick a plot type to represent you data, you need to know what the "take home message" for the audience is. Do you want to show contrast between two different results? Do you want to show evolution through time? Do you want to compare different categories? Do you want to show geospatial variations in data? 

### Rule 3: Adapt the Figure to the Support Medium

It's important to understand what medium the graphic or figure will be displayed in: are you preparing for a talk and will be showing your figures over a projector or a shared screen via a webconfereing tool? Will your figures be printed onto a poster for a conference? Will your figure be included in a journal or other publication and will be viewed online where its zoomable?

Figures shown in a presentation will only be visible to the audience for a short amount of time; they will not have time to read lots of labels and annotations, and a detailed and difficult to parse chart will leave the audience confused and will distract them from listening to your presentation. They will also be supported by your discussion points and presentation, so can be less detailed. Figures used in poster presentations will be printed out which can lead to issues in colour grading if screen-specific colourspace is used (e.g. RGB instead of CMYK) and resolution problems if rasterised images are used and not saved at a high enough dpi.

Points to keep in mind when designing your figure for different media:
- Size: what size do different components need to be in order to deliver your message in the chosen media? Think about:
    - Font size for axis labels and annotations
    - Line thickness
    - Marker size
- Detail(/clutter): in tandem with the choice of size for various plot elements, how visually cluttered is your figure? Readers of a paper may have time to zoom in and read multiple annotations and lables, while audience members at a presentation realistically only have a few seconds to absorb information from a plot.
- Colour choices: while colour choice is of course important generally when designing a useful and attractive plot, and in ensuring it is understandable to someone with colourblindness, it becomes especially important when considering where and how your figure is going to be viewed. Certain colours in RGB space cannot be reproduced in CMYK for printing, and so colours used can appear muddied and dull if not appropriately converted. Additionally, different screens and projectors can have different colour settings (e.g. warm light settings) which can make certain colours look more similar to the point of being almost indistinguishable.

### Rule 4: Captions Are Not Optional

### Rule 5: Do Not Trust the Defaults

### Rule 6: Use Color Effectively

### Rule 7: Do Not Mislead the Reader

### Rule 8: Avoid “Chartjunk”

### Rule 9: Message Trumps Beauty

### Rule 10: Get the Right Tool
