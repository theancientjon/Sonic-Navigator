# Sonic-Navigator
Created for 7MU009: Music Computing at the University of Wolverhampton.
(Link submitted in time for original deadline, but work will finish in time for 29/05/20 due to UOW's blanket COVID extension)

## DEVELOPING AUDIBLE SPACE-NAVIGATION FOR VISUALLY IMPAIRED PEOPLE

### INTRODUCTION
======

This document outlines the development process of creating a modular piece of software to enable people who are blind or visually impaired (VI) to safely navigate spaces using an audio-based interface. It will include discussion of candidate solutions, the process of identifying the final choice, and then analysis of the implemented code and conclusions to be drawn from the completed piece.

### THE PROBLEM IDENTIFIED
======

Through my training as an Audio Describer for the stage, it has become evident that there is a huge advantage to the instantaneous nature of visual context. The predominant part of a description is done in the fifteen to twenty minutes prior to the show, audibly narrating the physical layout of the set, props that would be used, and character's appearence and costume. All the things that a sighted person can pick up in a few seconds.

Additionally, as part of my work in Front of House in theatre, with a number of visually impaired patrons, I have seen how useful it may be to create an audible context to the navigating of space.

Current methods of navigating space for people with VI include using a cane or a service animal - neither of which are infallible, and the latter can be an issue, depending on the skill/discipline of the animal - or asking to be guided by a member of staff, assuming that someone is free, and potentially impacting the patron's need for independance.

As such I aim to create a solution that will allow a visually impaired person to be guided to specific points in a set space that is completely new to them using an audible guide.

### DISMISSED POSSIBILITIES
======

Initial thoughts included considering practical designs. With the cane being a prominant form of user interface, modifying one to speak might be an interesting solution. However, these are already starting to be developed - such as the WeWalk which was featured in the Smithsonian magazine in October last year - and are out of my skill level to design.

Additionally, the use of GPS in products such as this could be an issue. My own personal use of GPS is most extensively location-based video games such as Pokémon GO, and the cause for my concern is GPS drift, which is explained in this article from Jasmine Henry for GameRant:

> Problems with GPS drifting, which has reportedly been for several months, mean that Pokemon GO is unable to properly recognize where a player actually is. The game may wander off to a distant location far away from the player, causing a real headache. For example, if a player aims to take on a Gym but the game GPS drifts away from the location, they will have to do it all over again. Combined with soft bans that prevent them from re-battling the Gym for at least 10 minutes and Pokemon needing to be revived despite not having a "proper" shot at the Gym, and it's easy to see why so many are frustrated.

Whilst major drifting has been patched out through software updates, minor drift is still apparent. For a game being played by a sighted person, this can be compensated for. But for a visually impaired person, any literally misleading information could be dangerous.

Alternative fixed navigation systems do exist, such as what3words:

> We have assigned each 3m square in the world a unique 3 word address that will never change.
> For example ///filled.count.soap marks the exact entrance to what3words’ London headquarters.
> 3 word addresses are easy to say and share, and are as accurate as GPS coordinates. 
> 51.520847,  -0.19552100 ←→ /// filled.count.soap

Working with fixed co-ordinates could be beneficial, but what3words' scale of 3m squares is too large to assist in the finer levels of navigation someone with VI would need, and neither does the fixed cardinal directions compared to the varied angles of city planning. Additionally, to develop a new, tigher-focused system would not be viable in the timeframe.

More simple technological systems - such as adapting door opening chimes used by businesses - could have been viable. But in high traffic and noise sensitive environments, the concerns over disturbance leading to systems being shut off and not active when being relied on may result in injury and liability.

Finally, the module is taking place during the COVID-19 pandemic that has resulted in large scale quarantines, and the closure of most public buildings. Developing and testing a product designed to help the navigation of crowded spaces when theatres are closed and people are required to stand two metres apart is not currently possible.

As such, I shall be programming a representative part of space navigation using auditory responses, using one of two programming languages.

### PURE DATA VERSUS MAX 8: FINAL SELECTION RATIONALE
======

Experimentation and prototyping was done in both Pure Data and Max 8. Both were visual programming tools that operated in the same basic manner of patching text boxes with fixed terms to generate effects.

Pure Data was considered due to my having witnessed use of an XY data grid within a patch demonstration, and the open source nature of the hardware meant more time to trial and develop the software. However, the xy grid is an additional resource that may fall out of the parameters set within the module I am studying, and definitely fell out of my ability to use it correctly. Additionally, the threadbare nature of the interface added to the difficulty in navigating the process, and limited my ability to demonstrate elements as precisely.

I had not originally intended to use Cycling 74's Max 8, due to it being limited to a 30-day free trial and then - at its cheapest - $9.99/month. However, Max's stronger visual interface meant I could create a visual facsimile of an XY Grid via sliders. Additionally its in-built help resources demonstrated the basic operation of objects in a concise, replicable manner.

Both pieces of software could still be frustratingly obtuse, and translating my requirements into the codes needed to operate the functions thwarted me on several occasions. I will acknowledge that it is a poor worker who blames their tools, but it has to be noted that in neither program could I seem to find a way to create what was needed.

In the end, Max was the software that got the best job done.

### IMPLEMENTED SOLUTION IN CODE
======

The Max Patch is included within the repository. It is designed to create a varying tempo based on the XY Input of a 100 x 100 grid.

### EVALUATION OF CODE
======

What I have been able to create is essentially a Tempo Generator, which should - when hooked up to the correct audio generation software, create a "Warmer/Colder" sonic guidance to help visually impaired people navigate. Similar to a metal detector or geiger counter, where an increase in beeps indicates a growing proximity, and a decrease showing the inverse.

Using the sliders in the orientation of an axis really helps to make up for the lack of an actual XY interface. I had considered trying to add more visual detail, but thought any further attempt might lead to an expectation of the actual usage being available, and then frustrate when it did not work as one might hope.

Attempts to create a customisable XY field failed due to the creation of negative axis results, and being unable to find a way to mathematically negate the ensuing errors.

There are areas to be developed in this patch. I might look into feeding the maximum combined values into the code, instead of the fixed amount being sat out on its own. I had also hoped to have the audio output involved in this section of the patch. However, the solution eluded me. Though keeping this as a single module, and looking to develop the audio output as part of an interface that could be controlled by the user might be preferable. This would involve further testing, and benefit from feedback from the VI community, who are currently hard to access. 

### CONCLUSION
======

This is not wholly the product I intended to create, but I have built a modular section that could prove to be useful in creating a larger code or possibly a device that may benefit a community that would benefit from technological help. Given the circumstances of the project, I'm aware of the areas to be improved upon, but genuinely pleased with the result.

### REFERENCES
======
https://wewalk.io/en/
https://www.smithsonianmag.com/innovation/smart-cane-helps-blind-people-navigate-180973279/
https://gamerant.com/pokemon-go-gps-drift-problem/
https://what3words.com/about-us/
https://www.amazon.co.uk/WIRELESS-VISITOR-ENTRY-Magnet-Contact/dp/B06X94RWWF
