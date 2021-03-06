---
layout: default
title: Procurement Commodities Contracts
permalink: /commodities/
---

## PROCUREMENT COMMODITIES CONTRACTS

The contract information provided on this site represents contracts that are bid and awarded by the City’s Procurement Department.  These contracts are for supplies, equipment, non-professional services, and public works.  Examples of these types of contracts include but are not limited to:   office supplies, vehicles, landscaping services, various maintenance and construction.

Unlike Professional Services contracts, Procurement contracts are typically not negotiated but are subject to the lowest, responsive, responsible bidder requirements found in [Section 8-200](http://www.amlegal.com/nxt/gateway.dll/Pennsylvania/philadelphia_pa/philadelphiahomerulecharter/articleviiiprovisionsofgeneralapplicatio/chapter2contractsprocurementpropertyandr?f=templates$fn=default.htm$3.0$vid=amlegal:philadelphia_pa$anc=JD_Art.VIIICh.) of the Home Rule Charter.  As such, they must be awarded to the bidder offering the lowest price, whose bid meets the bid specifications (responsive) and who is also capable of the performance required under the contract (responsible).  These contracts are also known as “competitively bid contracts”.  Some specific points about Procurement contracts:


* The Procurement Department, not City operating departments, is the central agency responsible for managing the bid and contract execution process for the purchase of supplies, equipment, non-professional services, public works services, and concession agreements.
* Procurement contracts for non-professional services, supplies and equipment (referred to as “SS&amp;E” in the graphs and charts below) fall into two main categories: departmental and city-wide.  These contracts are typically awarded for a term of one year with up to three one-year renewals.  Our systems do not allow us to easily capture the data designated as departmental or city-wide. That designation is not listed on the data below.
* The Procurement Department manages the bid and contract execution process for public works contracts (referred to as “PW” in the graphs and charts below).   Generally, only five departments manage the public works projects once the contracts are signed. Those departments are Streets, Water, Public Property, Licenses and Inspections and the Airport. These contracts generally have multi-year terms and are not renewed.
* Procurement contracts that are valued at less than $32,000 within a fiscal year are referred to as “Small Order Purchases” or “SOPs” and are issued by individual departments.  These purchases are not listed below and account for approximately $7 Million dollars in annual spend.
* SOPs do not require a formal bid process but are still subject to the competitive bidding requirements and they cannot be renewed beyond the end of a fiscal year.

PLEASE NOTE - Contracts listed here are paid for by multiple sources, including but not limited to, state and federal funds, Water and Aviation funds and the City’s General Fund.  The amounts in the graphs below do not represent the amount paid to a particular vendor. See the last table for payment amounts for the 20 largest contracts by award amount for the reported quarter.

The charts and table below summarize procurement contract data for FY 2016, Q1. You can also download the entire data set in CSV format.

<a href="faq/" class="button">FAQ</a>
<a href="https://www.opendataphilly.org/dataset/commodity-contract-data" target="_blank" class="button">Download data</a>

  <div class="row">
    <div class="medium-24 columns">
      <h3 class="chart">Contracts by Contract Type</h3>
      <div id="by_type" class="visualization"></div>
    </div>
  </div>

  <div class="row">
    <div class="medium-24 columns">
      <h3 class="chart">Contracts by Vendor</h3>
      <div id="by_vendor" class="visualization"></div>
    </div>
  </div>

  <div class="row">
    <div class="medium-24 columns">
      <h3>Top 20 Contracts by Contract Amount</h3>
      <table id="browse" class="table table-striped"></table>
    </div>
  </div>

  <div class="row">
    <div class="medium-24 columns">
      <h3>Expiring Contracts</h3>
      <table id="expiring" class="table table-striped"></table>
    </div>
  </div>

<script type="text/javascript">
sources = [
    {
        path: '{{ "/commodities/data/FY2016Q1.csv" | prepend: site.baseurl }}',
        cleanCurrency: ['Contract_Amount', 'Total_Transactions'],
        visualizations: [
            {
                container: '#by_vendor',
                type: 'pie',
                groupBy: 'Vendor_Name',
                aggregate: 'Contract_Amount',
                limit: 10
            },
            {
                container: '#by_type',
                type: 'pie',
                groupBy: 'Contract_Type',
                aggregate: 'Contract_Amount',
                limit: 10
            },
            {
                container: '#browse',
                type: 'table',
                columns: {
                    'Department_Name': 'Department',
                    'Vendor_Name': 'Vendor',
                    'Contract_Type': 'Type',
                    'Contract_Description': 'Description',
                    'Contract_Amount': 'Contract Amount',
                    'Total_Transactions': 'Payments'
                },
                sort: [
                    [4, 'desc']
                ]
            },
            {
                container: '#expiring',
                type: 'table_expired',
                columns: {
                    'Contract_Number': 'Contract Number',
                    'Contract_Description': 'Description',
                    'Start_Date': "Start Date",
                    'End_Date': "End Date",
                    'Contract_Type': 'Type',
                    'Vendor_Name': 'Vendor',
                    'Department_Name': 'Department',
                    'Contract_Amount': 'Contract Amount',
                    'Total_Contract_Months': 'Total Contract Months',
                    'Remaining_Contract_Months': 'Remaining Contract Months',
                },
                sort: [
                    [4, 'desc']
                ]
            }
        ]
    }
];
</script>
