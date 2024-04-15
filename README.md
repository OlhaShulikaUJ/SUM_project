# Seamless Shared Urban Mobility (SUM)
> This software allows performing simulations of trip requests and various travel scenarios within the specified study area, and using obtained KPIs for determining utilities of the integration of New Shared Modes and PT.
## Technology
The software was implemented using Python programming language and its basic libraries
## Description
### The developed framework based on two main developed libraries:
* [Public Transport queries](https://github.com/RafalKucharskiPK/query_PT)
* [ExMAS](https://github.com/RafalKucharskiPK/ExMAS/tree/master/ExMAS)
### A module 'The parameter-free comparison of selected areas for Krakow' consist of:
* [PT_mode](https://github.com/OlhaShulikaUJ/SUM_project/tree/main/PT)
* [NSM+PT_mode](https://github.com/OlhaShulikaUJ/SUM_project/tree/main/NSM%2BPT)
### The roadmap of the current project for the city:
1) OD 
   * sample origins
   * sample destinations
     
2) Demand for PT
   
3) Utility of PT for trips from O to D: $U_{PT:O\to \overline{D}}$

4) Utility of PT for trips from HUB to D: $U_{PT:HUB\to \overline{D}}$

5) ExMAS for all PT users from O to HUB:

$$
\begin{aligned}
 U_{SUM}=U_{PT:HUB\to \overline{D}} + \underbrace{\beta _{t}\beta _{s}\left ( t _{t}+ \beta _{w}t _{w}\right)}+ASC
\end{aligned}
$$

6) Model Choise

7) Demand for SUM
