# Querying XML values using Python

A quick overview of important XML queries using Python.

## Basic Python snippets for querying XML

Here is a basic XML snippet:

```XML
<Animals>
	<Mammal>
		<Rabbit lifespan_yrs = "2" sleep_time_hrs = "8">
			<Description available = "True">Plant-eating mammal, with long ears, long hind legs, and a short tail</Description>
		</Rabbit>
		<Cow lifespan_yrs = "18" sleep_time_hrs = "4">
			<Description available = "True">Fully grown female animal of a domesticated breed of ox, kept to produce milk.</Description>
		</Cow>
		<Dog lifespan_yrs = "10" sleep_time_hrs = "12">
			<Description available = "True">Domesticated carnivorous mammal that has a long snout, an acute sense of smell, non-retractable claw</Description>
		</Dog>
	</Mammal>
	<Reptile>
		<Snake family = "Boidae" lifespan_yrs = "25" sleep_time_hrs = "16">
			<Description available = "False"></Description>
		</Snake>
		<Snake family = "Biperidae" lifespan_yrs = "15" sleep_time_hrs = "16">
		    <Description available = "True">Venomous snake that attains a length of about two feet, varies in color and is usually not fatal to humans</Description>
		</Snake>
		<Iguana lifespan_yrs = "15" sleep_time_hrs = "12">
			<Description available = "True">Large, arboreal lizard which has stout legs and a crest of spines from neck to tail</Description>
		</Iguana>
	</Reptile>
	<Fish>&lt;?xml version="1.0"?&gt;
		&lt;Shark&gt;
			&lt;Description&gt;A long-bodied chiefly marine fish with a cartilaginous skeleton&lt;/Description&gt;
		&lt;/Shark&gt;
	</Fish>
</Animals>
```

#### query overall XML
```Python
SELECT
	[nature].query('(/*/Mammal)') AS 'Mammal'
FROM   
        [nature].[living_creatures]
```

>|       Mammal	       |
>| ------------------- |
>| ``` <Mammal><Rabbit lifespan_yrs="2" sleep_time_hrs="8"><Description>Plant-eating mammal, with long ears, long hind legs, and a short tail</Description></Rabbit><Cow lifespan_yrs="18" sleep_time_hrs="4"><Description>Fully grown female animal of a domesticated breed of ox, kept to produce milk.</Description></Cow><Dog lifespan_yrs="10" sleep_time_hrs="12"><Description>Domesticated carnivorous mammal that has a long snout, an acute sense of smell, non-retractable claw</Description></Dog></Mammal>```|
