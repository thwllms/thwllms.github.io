---
layout:     post
title:      "Prometheus' Carbon Capture Claims"
date:       2019-05-21 22:20:00
summary:    Some back-of-the-envelope calculations.
categories: blog
---

Climate change is something I find myself fretting about from time to time. Two
hundred years from now I think it might be regarded as the driving issue of the
21st century. The scale of climate change is difficult to grasp intuitively.
Many solutions are touted (renewable energy, carbon capture, geoengineering,
etc.), but without putting them in context it's hard to understand how effective
they might actually be.

A couple weeks ago the founder of a company called Prometheus posted a [thread
on Hacker News](https://news.ycombinator.com/item?id=19842240) introducing his
company's technology, which converts CO<sub>2</sub> into gasoline and other
fuels. Apparently they grab CO<sub>2</sub> from the air, mix it with water, do
some fancy chemistry to turn the CO<sub>2</sub> into alcohols, extract the
alcohols using a carbon nanotube membrane, and up-convert the alcohols into
fuel.

A good portion of the thread is about electricity costs, fuel costs, and the
viability of Prometheus as a business. A bit deeper in the conversation the
founder mentioned that they "expect a gallon of gasoline to require 60 kWh of
electrical energy."

This got me wondering - if this process was infinitely scalable, how much energy
would it take to make the entire planet carbon-neutral? In other words, what if
we simply stored the resulting gasoline instead of burning it? Humankind emits
something like [36 gigatonnes of CO<sub>2</sub> per
year](https://www.co2.earth/global-co2-emissions). At 60 kWh per gallon of
gasoline produced by Prometheus' technology, what would it take to get from 36
gigatonnes of emissions to zero?

Here's a basic equation:

```
co2_removed = co2_per_gallon * (1/energy_per_gallon) * total_energy
```

Where:
* `co2_removed`: kilograms of carbon removed by the process.
* `co2_per_gallon`: kilograms of CO<sub>2</sub> removed from the atmosphere to
  create a gallon of gasoline.
* `energy_per_gallon`: kilowatt-hours required to produce one gallon of
  gasoline.
* `total_energy`: kilowatt-hours consumed by the process.

Rearranging to solve for `total_energy`:

```
total_energy = co2_removed * energy_per_gallon / co2_per_gallon
```

One gallon of gasoline converts to about [20 lbs (9.1 kg) of
CO<sub>2</sub>](https://www.fueleconomy.gov/feg/contentIncludes/co2_inc.htm)
when burned; for simplicity we'll also assume that Prometheus' technology
removes that same amount of CO<sub>2</sub> per gallon of gasoline produced.  To
make things really simple, we'll assume that the energy used by the process
comes from carbon-neutral sources.

```
total_energy = 36*10^12 kg * 60 kWh/gal / 9.1 kg/gal
```

We get `2.4*10^14 kWh`, or 24,000 TWh. By comparison, [in 2017 the United
States produced 4,282 TWh of electricity, and worldwide production was 25,551
TWh](https://en.wikipedia.org/wiki/List_of_countries_by_electricity_production).
In other words, this process would consume **56 times the current US electrical
generating capacity**, and **9 times the current world electrical generating
capacity**.

Even if Prometheus' technology removes many, many times more CO<sub>2</sub> per
gallon of gasoline produced, we're still talking sci-fi levels of energy.

If, somehow, we could produce that much energy to scale the process, what would
we do with all the gasoline? Assuming the same 9.1 kg CO<sub>2</sub> per gallon
figure, we'd end up with roughly `4*10^12` gallons of gasoline, or 3.6 cubic
miles. That's almost enough to fill [Seneca
Lake](https://en.wikipedia.org/wiki/Seneca_Lake_(New_York)).

Oof. Hopefully I'm off... by many orders of magnitude.
