---
layout: about
title: Tutoring 
description: Ivar Rydstrom's Private Tutoring Services
breadcrumbs: true
---
<script>
    function copy_to_clipboard() {
        navigator.clipboard.writeText('irydstrom@berkeley.edu');
        var tooltip = document.querySelector(".copy_tooltip");
        tooltip.innerHTML = "Copied ✓";
    }
</script>
For tutoring inquiries, please email me directly at ***irydstrom@berkeley.edu***{:.copy_clip onclick="copy_to_clipboard()"}

<script>
    var copy_clip = document.querySelector(".copy_clip");
    var tooltip = document.createElement("span");
    tooltip.innerHTML = "Copy Text";
    tooltip.setAttribute("class","copy_tooltip");
    copy_clip.appendChild(tooltip);
    copy_clip.addEventListener("mouseout",function() {
        document.querySelector(".copy_tooltip").innerHTML = "Copy Text";        
    })
</script>

I offer private one-on-one tutoring services tailored for college and high school physics courses. I have nearly 500 sessions of experience, and have developed extensive problem solving methods students can use to solve nearly any basic physics problem they may encounter.

## Equation Sheets

*All equation sheets on this page are written by Ivar Rydstrom, unless otherwise stated.* *Digital transcription of hand-written equation sheets is currently underway.*{:style="color:red"}

{% include sheet-category.html name="mechanics 🔨" id="collapsible-mech" titles="AP Physics C Equation Sheet (College Board), Advanced Analytical Mechanics" slugs="apC, PHYS104" previews="2, 2" %}

{% include sheet-category.html name="electricity & magnetism 🔌" id="collapsible-EM" titles="Introductory E&M (Dr. Young), Electrodynamics" slugs="PHYS33-dryoung, PHYS112" previews="1, 2" %}

{% include sheet-category.html name="thermodynamics ♨️" id="collapsible-thermo" titles="Thermodynamics, Statistical Mechanics" slugs="PHYS32, PHYS120" previews="2, 1" %}

{% include sheet-category.html name="quantum mechanics 💎" id="collapsible-quantum" titles="Quantum Mechanics, Quantum Electrodynamics" slugs="PHYS121, PHYS123" previews="2, 1" %}

{% include sheet-category.html name="vector calculus ➡️" id="collapsible-vector" titles="Vector Calculus, Vector Calculus Reference (Griffiths E&M)" slugs="MATH14, Griffiths-Vector-Calc" previews="2, 1" %}

{% include sheet-category.html name="linear algebra 🔢" id="collapsible-linear" titles="Advanced Linear Algebra" slugs="MATH103" previews="2" %}

---

<br>

<!--author-->