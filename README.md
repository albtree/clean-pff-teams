# clean-pff-teams
Function to clean Pro Football Focus (PFF) College Football Team Names to those used by College Football Data (CFBD) - for the level of FBS only. Future plans may include to add FCS teams. Likely to be used alongside the cfbfastR package.

**Example**
If pff_dataframe is an example dataframe that includes PFF team names under the variable name - team_name

```
# A tibble: 6 × 1
  team_name 
  <chr>     
1 AIR FORCE 
2 AKRON     
3 ALABAMA   
4 APP STATE 
5 ARIZONA   
6 ARIZONA ST

pff_dataframe$teams_cleaned <- clean_teams_pff_to_cfbd(pff_dataframe$team_name)

> head(pff_dataframe)
# A tibble: 6 × 2
  team_name  teams_cleaned    
  <chr>      <chr>            
1 AIR FORCE  Air Force        
2 AKRON      Akron            
3 ALABAMA    Alabama          
4 APP STATE  Appalachian State
5 ARIZONA    Arizona          
6 ARIZONA ST Arizona State    
```

Or using an example using dplyr

```
# A tibble: 6 × 1
  team_name 
  <chr>     
1 AIR FORCE 
2 AKRON     
3 ALABAMA   
4 APP STATE 
5 ARIZONA   
6 ARIZONA ST

pff_dataframe <- pff_dataframe |> mutate(teams_cleaned = clean_teams_pff_to_cfbd(team_name))

> head(pff_dataframe)
# A tibble: 6 × 2
  team_name  teams_cleaned    
  <chr>      <chr>            
1 AIR FORCE  Air Force        
2 AKRON      Akron            
3 ALABAMA    Alabama          
4 APP STATE  Appalachian State
5 ARIZONA    Arizona          
6 ARIZONA ST Arizona State 
```

