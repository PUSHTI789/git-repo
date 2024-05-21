#### Scenario: Returning values when Return value type is "P" i.e. Position 
> **Given** Lookup type is Number with Name ”Transaction Names” and lookup table as below :
> | From | to | Return Value |
> | -- | -- | -- |
> | 1    | 10 | 55           |
> | 10   | 30 | 100          |
> | 30   | 50 | 200          |
>
> **When** AMATCH(5,""Transaction Names"",TODAY(),""P"") is called
>
> **Then** Return value should be 1
>
>  **When** AMATCH(1,""Transaction Names"",TODAY(),""P"") is called
>
>  **Then** Return value should be 1
>
>  **When** AMATCH(10,""Transaction Names"",TODAY(),""P"") is called
>
>  **Then** Return value should be 1
>
>  **When** AMATCH(30,""Transaction Names"",TODAY(),""P"") is called
>
>  **Then** Return value should be 2
>
>  **When** AMATCH(0,""Transaction Names"",TODAY(),""P"") is called
>
>  **Then** Return value should be 0
>
>  **When** AMATCH(75,""Transaction Names"",TODAY(),""P"") is called
>
>  **Then** Return value should be 0"

#### Deleting KPIs that are been used only in Bonus Payouts

> **Given** the KPIs that are referred
>  |  KPI  |  METHODS  |
>  |  --  | -- |
>  |  Transaction KPI | Marginal or Progressive or Interpolated Marginal or Simple or Filter: include or exclude Methods 
>  |  Dynamic kpi  |  Marginal or Progressive or Interpolated Marginal or Simple or Filter: include or exclude Methods
>  |  class kpi   | Marginal or Progressive or Interpolated Marginal or Simple or Filter: include or exclude Methods 
>  |  group kpi   | Marginal or Progressive or Interpolated Marginal or Simple or Filter: include or exclude Methods 
> 
> **When** user tried to Delete any of these KPIs
>
> **Then** it should show error message 'Remove reference ""KPI name"" from below Payouts'
