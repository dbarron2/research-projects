# Research Project: An Animated Pie Chart of the Universe

## Project overview

In this project, you will create a visual model of how the contents of the universe change over cosmic time.

Today, cosmologists often describe the universe as being made mostly of dark energy, matter, and a very small amount of radiation. But this was not always true. In the early universe, radiation was much more important. Later, matter became dominant. More recently, dark energy became the dominant component of the cosmic energy budget.

Your main goal is to create an **animated GIF of a pie chart** showing how the fractional contents of the universe evolve with time. This is a visualization project, a coding project, and a physics project. To make the animation correctly, you will need to learn how different forms of energy density behave as the universe expands.

This project is designed for beginning physics, astronomy, or astrophysics students. You are not expected to know advanced cosmology at the start. However, by the end of the project, you should be able to explain the basic physical ideas behind the evolution of the cosmic energy budget, and you should have strengthened your ability to use Python for scientific visualization and computation.

---

## Main scientific and technical goals

By completing this project, you should learn to:

1. Explain what cosmologists mean by the **scale factor**, usually written as \(a\).

2. Explain the relationship between **scale factor** and **redshift**, usually written as \(z\).

3. Understand the basic components of the standard cosmological model:
   - radiation,
   - matter,
   - dark energy.

4. Learn how the energy densities of these components change as the universe expands.

5. Compute the fractional contribution of each component to the total energy density of the universe.

6. Connect the contents of the universe to the Hubble expansion rate.

7. Create clear scientific plots and animations using Python.

8. Improve your ability to write readable, well-commented scientific code.

9. Explain, in words, what your visualization teaches about the history of the universe.

---

## Core idea

The universe expands over time. As it expands, different components of the universe become more or less important.

Your task is to find out, from the cosmology resources, how radiation, matter, and dark energy change as the universe expands. Once you understand those scalings, you will use them to calculate the fractional energy budget of the universe at different times.

The animated pie chart should not simply guess or interpolate between an “early universe” pie chart and a “today” pie chart. It should be based on the physical evolution of the different components.

---

## Required products

At the end of the project, you should produce:

- **An animated GIF of the cosmic energy budget**  
  This should show a pie chart of the fractional contributions of radiation, matter, and dark energy as the universe evolves. Each frame should be clearly labeled with a useful time variable, such as scale factor \(a\), redshift \(z\), or cosmic time if you complete that stretch goal.

- **A static plot of the fractional energy densities**  
  This should show how the fractional contributions of radiation, matter, and dark energy change with scale factor or redshift. This plot should help identify when each component dominates.

- **A static plot of the Hubble expansion rate**  
  This should show how the expansion rate of the universe changes as a function of scale factor or redshift. The goal is to connect the contents of the universe to the expansion history.

- **A short written explanation**  
  This should explain what your animation and plots show. It should describe the physical meaning of radiation domination, matter domination, and dark-energy domination, and it should explain why the relative importance of the components changes over time.

- **A clean Python notebook or script**  
  This should generate your calculations, plots, and animated GIF. The code should be readable, well organized, and clearly commented. Part of the purpose of this project is to practice writing Python code that another scientist could understand and reuse.

---

## Suggested workflow

### Step 1: Learn the basic vocabulary

Before writing code, make sure you understand the following terms:

- universe expansion
- scale factor
- redshift
- energy density
- critical density
- density parameter \(\Omega\)
- radiation
- matter
- dark energy
- Hubble expansion rate
- Friedmann equation

You do not need to understand every detail at a graduate level. Your goal is to understand these ideas well enough to explain what your plots mean.

---

### Step 2: Find the relevant cosmological scalings

Use the recommended cosmology resources to determine how radiation, matter, and dark energy scale as the universe expands.

As you read, pay attention to the physical reason behind each scaling. Do not just copy equations into your code. Make sure you can explain, in words, why different components behave differently.

You should be able to answer:

- Why does matter dilute as the universe expands?
- Why does radiation dilute differently from matter?
- Why does dark energy behave differently from both matter and radiation?
- What does it mean for one component to dominate the total energy density?

---

### Step 3: Choose present-day cosmological parameters

You will need present-day values for the density parameters. For a first version, it is acceptable to use approximate values from a textbook or standard cosmology reference.

You should clearly state which values you used and where they came from.

Do not worry if your numbers are slightly approximate. For this project, the conceptual behavior is more important than high-precision parameter fitting.

---

### Step 4: Compute the fractional energy budget

Choose a range of scale factors or redshifts. Today corresponds to \(a = 1\). Earlier times correspond to smaller values of \(a\), or equivalently larger values of \(z\).

For each time, compute the relative contribution of radiation, matter, and dark energy to the total energy density.

Your fractional contributions should always add up to 1. This is an important check on your calculation.

---

### Step 5: Make the static plots first

Before making the animated GIF, make the static plots.

At minimum, make:

- a plot of the fractional energy densities versus scale factor or redshift
- a plot of the Hubble expansion rate versus scale factor or redshift

These plots are your sanity checks. If they do not make physical sense, the animation will not be meaningful.

You should check that:

- radiation dominates at early times
- matter dominates at intermediate times
- dark energy dominates at late times
- the fractions always add up to 1

---

### Step 6: Create the animated pie chart

Once your calculations and static plots are working, create the animated GIF.

The animation should be clear and readable. Think carefully about:

- labels
- colors
- title
- frame rate
- whether to show \(a\), \(z\), or cosmic time
- whether small components are visible
- whether the scientific message is understandable

The final GIF should be something you could show to another beginning student to explain how the universe changes over time.

---

### Step 7: Write the explanation

Your short written explanation should not just describe what you did. It should explain what you learned.

It should answer questions such as:

- What are the main components of the universe in this model?
- Why does the pie chart change over time?
- What is radiation-matter equality?
- What is matter-dark-energy equality?
- What does the Hubble expansion rate plot show?
- What is the difference between an absolute density and a fractional density?
- What was the most important physics idea you learned from making the visualization?

---

## Recommended resources

### Primary resource

**Barbara Ryden, _Introduction to Cosmology_**

This is the main recommended textbook for the project. Focus on the sections introducing:

- the expansion of the universe
- scale factor and redshift
- the Friedmann equation
- radiation, matter, and dark energy
- the changing energy budget of the universe

### Additional useful resources

**Andrew Liddle, _An Introduction to Modern Cosmology_**

This is a concise introductory cosmology text. It may be useful if you want a shorter second explanation of the same ideas.

**Ned Wright’s Cosmology Tutorial**

This is a freely available online cosmology resource with useful explanations of redshift, expansion, cosmological parameters, and distances.

### Optional numerical reference

**Planck 2018 cosmological parameters**

Use this only if you want more precise modern parameter values. You do not need to understand the whole paper for this project.

---

## Stretch goal 1: Convert scale factor to cosmic time

For the main version of the project, it is acceptable to label the animation by scale factor \(a\) or redshift \(z\). However, a more physically intuitive animation would label frames by the approximate age of the universe.

To do this, you need to convert scale factor into cosmic time.

This requires using the expansion history \(H(a)\). You should investigate how the expansion rate of the universe determines the relationship between scale factor and cosmic age.

Your goal is to understand what this conversion means physically: it connects the expansion history of the universe to the amount of time that has passed.

If you complete this stretch goal, your GIF could label frames with approximate ages such as:

- early universe
- hundreds of thousands of years
- millions of years
- billions of years
- today

Be careful: equal spacing in scale factor is not the same as equal spacing in cosmic time.

---

## Stretch goal 2: Include neutrinos

The basic project may group all radiation together. As a bonus challenge, investigate how neutrinos should be treated.

This is more subtle than the photon radiation component because neutrinos behave like radiation when they are highly relativistic, but massive neutrinos can behave more like matter at late times.

Your goal for this stretch section is not necessarily to build a perfect neutrino model. Instead, your goals are to:

1. Learn why neutrinos are part of the cosmic energy budget.
2. Understand why their scaling with expansion is more complicated than photons.
3. Decide on a reasonable approximation.
4. Clearly state and justify the approximation you use.

Possible approaches include:

- treating neutrinos as part of the radiation density at early times
- including a simple effective relativistic-neutrino contribution
- discussing qualitatively why massive neutrinos require a more careful treatment

If you include neutrinos in your animation or plots, make sure your written explanation clearly says what approximation you used.

---

## Final deliverables

Submit the following:

- Animated GIF of the cosmic energy-budget pie chart
- Static plot of the fractional energy densities
- Static plot of the Hubble expansion rate
- Clean Python notebook or script
- Short written explanation of the science behind the project

Optional bonus deliverables:

- A version of the GIF labeled by cosmic time
- A version of the calculation or written discussion that includes neutrinos

---

## What a successful project should demonstrate

A successful project does not need to be complicated. It should be clear, correct, and well explained.

By the end, you should be able to say:

- I understand why the contents of the universe appear to change over time.
- I understand how radiation, matter, and dark energy behave differently as the universe expands.
- I can compute the fractional contribution of each component at different times.
- I can connect the energy contents of the universe to the Hubble expansion rate.
- I can use Python to create clear scientific plots and animations.
- I can explain what my visualization shows to another beginning student.

The goal is not just to make a plot. The goal is to use a plot to understand the physical story of the universe.
