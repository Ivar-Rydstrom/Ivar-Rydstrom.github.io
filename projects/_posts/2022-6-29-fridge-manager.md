---
layout: post
title: Custom Web GUI for Cryostat Control
image: /assets/images/fridge_gui/cooldown2_big.png
description: A custom web-based application for managing cryostats, built in Python Streamlit
category: projects
permalink: /projects/fridge-manager
related_posts: ""
tags: [computer science, physics]
---
## Cryostat Control

In order to cool samples in the lab down to millikelvin temperatures it requires the use of a cryostat. These devices exploit thermodynamics involving Helium-3 (*3He*) and Helium-4 (*4He*), two different isotopes of Helium,  which enable small solid-state samples to achive temperatures of mere fractions of a kelvin, quite near absolute zero.

The kind of cryostats I have the most familiarity with are dry "3He Fridges". These fridges use a sorbtion pump to control the deployment of expensive 3He, eliminating the need to externally feed fresh Helium in the process of a cycle. That being said, they require complex thermodynamic cycling procedures in order to cool down, and can only acheive temperatures of about ~300mK (compared to the ~10mK base temperatures of [modern dilution refrigerators](https://nanoscience.oxinst.com/assets/uploads/NanoScience/Brochures/Principles%20of%20dilution%20refrigeration_Sept15.pdf)). [Learn more about 3He refrigerators here](https://liquids.seas.harvard.edu/penanen/workings.html).

![3He Canister](/assets/images/fridge_gui/3he_square.jpg){:.center-img style="width:65%;height:auto"}
*Regulation canister containing $70,000 of Helium-3.*{:.caption}

## Graphical User Interface for Cryostat Control

My group at SLAC needed a way to control an old 3He cryostat that was being overhauled for the purpose of testing [SPLENDOR project](/projects/filter-box#splendor) components. The goal was to create a more automated and streamlined interface that would override the manual instrument controls used.

Using the Python framework [Streamlit](https://streamlit.io/), collegue Makar Dubovskov and I created a graphical user interface accessible over the web which relays essential telemetry data of various cryostat temperature and pressure sensors. It while simultaneously displaying it live, it logs this data locally on the fridge server and allows for archival data analysis. Additionally, it allows users to easily set individual heater and gas-gap switch voltages, which streamlines the fridge cycling process significantly and enables full remote control of the cryostat.

It was built entirely in Python Streamlit, and features asynchronous multi-process coordination to manage different individual tasks separately, from data stream logging to browser request handling.

![Web Interface](/assets/images/fridge_gui/full_gui.png){:.center-img style="width:100%;height:auto"}
*Full Fridge Manager web GUI monitoring a cryostat at base temperature.*{:.caption}