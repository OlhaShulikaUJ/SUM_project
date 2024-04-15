# Seamless Shared Urban Mobility (SUM)
> This software allows performing simulations of trip requests and various travel scenarios within the specified study area, and using obtained KPIs for determining utilities from the integration of New Shared Modes and PT.
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
3) Utility of PT for trips from O to D (PT:O→D)
4) Utility of PT for trips from HUB to D (PT:Hub→D)
5) ExMAS for all PT users from O to HUB

U_{SUM}=U_{PT:HUB\to \overline{D}} + \underbrace{\beta _{t}\cdot \beta _{s} (t_{t}+\beta _{w}t_{w})}+ASC
$U^s_{i, r_k} = \beta_c (1 - \lambda_s)\lambda l_i + \beta_t \beta_s (\hat{t}_i + \beta_d \hat{t}^p_i) + \varepsilon$

$U{SUM}=(1+x)^2$
