<script>
        import Chart from 'svelte-frappe-charts';

        let bike_rebate_data = {
        labels: ["0", "1", "2", "3", "4", "5", "6", "7", "8", "9", "10"],
        datasets: [
          {
            name: "Returns",
            values: ["0", "15000", "30000", "45000", "60000", "75000", "90000", "105000", "120000", "135000", "150000"],
            // values: [...Array((Math.ceil(payback_years)+4)).keys()].map(multiplySavingsKept),
            chartType: 'line',
            lineOptions: { regionFill: 1}
          },
          { name: "Investment", 
            values: ["2000"],
          },
          // {
          //   values: [cost_per_user],
          // }
        ],
        // yRegions: [{ label: "Region", start: 100, end: 4000 }],
        // yMarkers: [
        //       {
        //           label: "Project Cost",
        //           value: cost_per_user,
        //           options: { labelPos: 'left' } // default: 'right'
        //       }
        //   ]
      };

      let cepp_data = {
        labels: ["0", "1", "2", "3", "4", "5", "6", "7", "8", "9", "10"],
        datasets: [
          { name: "Returns",
            values: ["0", "24", "48", "72", "96", "120", "144", "168", "192", "216", "240"],
            // values: [...Array((Math.ceil(payback_years)+4)).keys()].map(multiplySavingsKept),
            chartType: 'line',
            lineOptions: { regionFill: 1}
          },
          { name: "Investment",
            values: ["0", "15", "30", "45", "60", "75", "90", "105", "120", "135", "150"],
          },
          
          // {
          //   values: [cost_per_user],
          // }
        ],
      //   tooltipOptions: [{
      //       formatTooltipY: (d) => d + " pts"
      // }]
        // yRegions: [{ label: "Region", start: 100, end: 4000 }],
        // yMarkers: [
        //       {
        //           label: "Project Cost",
        //           value: cost_per_user,
        //           options: { labelPos: 'left' } // default: 'right'
        //       }
        //   ]
      };

      let noFill =  {
          regionFill: 0 // default: 0
          }
      
          let fill =  {
          regionFill: 1 // default: 0
          }

      let ebike_investment = 1;
      let ebike_investment_unit = 1000000000;
      let cepp_investment = 150;
      let cepp_investment_unit = 1000000000;
      let displayPreview = true;
</script>
<svelte:head>
  <title>Anti-Inflationary US 🇺🇸</title>

  
  <meta name="description" content="The best policies for reversing inflation, balancing the federal books, and saving Americans money.">
  
  <!-- Facebook Meta Tags -->
  <meta property="og:url" content="https://sambutler.us/community-energy-vision/">
  <meta property="og:type" content="website">
  <meta property="og:title" content="Anti-Inflationary US 🇺🇸">
  <meta property="og:description" content="The best policies for reversing inflation, balancing the federal books, and saving Americans money.">
  <meta property="og:image" content="/solar_shelter.jpeg">
  
  <!-- Twitter Meta Tags -->
  <meta name="twitter:card" content="summary_large_image">
  <meta property="twitter:domain" content="sambutler.us">
  <meta property="twitter:url" content="https://antiinflationary.com">
  <meta property="og:title" content="Anti-Inflationary US 🇺🇸">
  <meta property="og:description" content="The best policies for reversing inflation, balancing the federal books, and saving Americans money.">
  <meta name="twitter:image" content="/solar_shelter.jpeg">
</svelte:head>

<div style="text-align: center;">
<h1>Anti-inflationary US 🇺🇸</h1>
<p>The best policies for reversing inflation, balancing the federal books, and saving Americans money.</p>
</div>
<br>
<section class="policies">
  <div style="margin-left: auto; text-align: right; margin-right: 10px;">
  <!-- <span style="background: rgb(229 229 229); border-radius: 10px; padding: 2px 5px;">Coming soon</span> -->
  <select><option selected>Sort by $ saved</option><option disabled>More coming soon!</option></select>
  <!-- {#if displayPreview}
  <span style="display: block; width:fit-content; margin-left: auto; margin-bottom: 5px; background: #f9f9f9; border-radius: 10px; padding: 2px 5px">Coming soon</span>
  {/if}
  <select on:hover={function() {console.log('test');}} on:mouseleave={function() {console.log('test');}} disabled style="cursor: pointer;"><option selected>Sort by $ saved</option></select> -->
</div>
<br>
<div class="policy">
  <h2>E-bike and bike rebates   <span style="vertical-align: sub; margin-left: 5px;"><svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-bike" width="32" height="32" viewBox="0 0 24 24" stroke-width="1.5" stroke="#597e8d" fill="none" stroke-linecap="round" stroke-linejoin="round">
    <path stroke="none" d="M0 0h24v24H0z" fill="none"/>
    <circle cx="5" cy="18" r="3" />
    <circle cx="19" cy="18" r="3" />
    <polyline points="12 19 12 15 9 12 14 8 16 11 19 11" />
    <circle cx="17" cy="5" r="1" />
  </svg> <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-bike hide-mobile" width="32" height="32" viewBox="0 0 24 24" stroke-width="1.5" stroke="#597e8d" fill="none" stroke-linecap="round" stroke-linejoin="round">
    <path stroke="none" d="M0 0h24v24H0z" fill="none"/>
    <circle cx="5" cy="18" r="3" />
    <circle cx="19" cy="18" r="3" />
    <polyline points="12 19 12 15 9 12 14 8 16 11 19 11" />
    <circle cx="17" cy="5" r="1" />
  </svg></span></h2>
  <p>Rebates towards the purchase of e-bikes, bicycles, and e-cargo bikes, which can be redeemed <strong>at time of purchase.</strong>  (If it's a deduction, people will be less likely to use the rebate, which limits the anti-inflationary benefits.)</p>
  <h3>For every <span class="invested">$2000 invested</span>, e-bike and bike rebates return <span class="returns">$150,000 in savings</span> over a ten-year period.</h3>
  <p>Investing $<input type="number" style="width: 40px" bind:value={ebike_investment}> <select bind:value={ebike_investment_unit}><option value={1000000}>million</option><option value={1000000000} selected>billion</option></select> into e-bike and bike rebates, generates <span class="returns">${(ebike_investment * 75 * ebike_investment_unit).toLocaleString()} in savings</span>.</p>
  <Chart data={bike_rebate_data} type="line" lineOptions={fill} colors={['green', 'purple']}/>
  <p>⚡ For the same amount of batteries used in one $70,000 electric truck, we can produce <strong>250+ electric bikes worth $1,000,000</strong>.</p>
<ul style="list-style: circle; margin-left: 20px;">
  <li>
      The F-150 Lightning battery weighs <a href="https://fordauthority.com/2021/05/2022-ford-f-150-lightning-battery-reportedly-weighs-1800-pounds/">1,800 pounds</a>, compared to the average e-bike battery weight of <a href="https://www.sixthreezero.com/blogs/bike-advice/how-much-does-an-electric-battery-weigh-or-how-heavy-are-e-bike-batteries">7 pounds</a>.
    </li>
  </ul>
  <p>Sources of data:</p>
  <ul>
    <li>The average cost of owning a car is <a href="https://www.nerdwallet.com/article/loans/auto-loans/total-cost-owning-car">$9,666 per year</a>.
      <ul>
        <li>Across 130 million commuters in the USA, that costs us $1.3 trillion per year.</li>
      </ul>
    </li>
    <li>State and local governments pay <a href="https://www.urban.org/policy-centers/cross-center-initiatives/state-and-local-finance-initiative/state-and-local-backgrounders/highway-and-road-expenditures">$617 per capita</a> on highways and roads every year.
      <ul>
        <li>With 329 million people in the United States, that costs us $203 billion every year.</li>
      </ul>
    </li>
    <li>The total we pay for parking in the United States amounts to <a href="https://usa.streetsblog.org/2017/07/26/if-americans-paid-for-the-parking-we-consume-wed-drive-500-billion-fewer-miles-each-year/">$2,300 per vehicle</a>.
      <ul>
        <li>With 230 million vehicle in the US, we pay approximately $529 billion every year on parking spaces.</li>
      </ul>
    </li>
    <li>Adding these figures together, we spend approximately $2 trillion per year on car infrastructure, including the costs of car ownership, road and highway expenditures, and the costs of parking (incl. real estate lost to parking spaces).
    </li>
    <li>With 130 million commuters in the US, we can save $15,000 every year for each commuter that transitions from cars to bikes.</li>
    <li>If an e-bike rebate costs $2000 per commuter, over a ten-year period, that is approxiamately $150,000 in savings generated by each rebate.
    </li>
  </ul>
</div>
<br>
<div class="policy">
  <h2>Clean Electricity Performance Plan</h2>
  <p>Give money to utilities who increase renewable energy capacity, and fine utilities who fail to do so.</p>
  <h3>For every <span class="invested">$150 billion invested</span>, the clean electricity performance plan returns <span class="returns">$432 billion in savings</span>.</h3>
  <h3>For every <span class="invested">$150 billion invested</span>, the clean electricity performance plan generates <span class="returns">$907 billion of economic value</span>.</h3>
  <p>Investing $<input type="number" style="width: 40px" bind:value={cepp_investment}>
    <select bind:value={cepp_investment_unit}><option value={1000000000} selected disabled>billion</option></select> into a Clean Electricity Performance Plan generates <span class="returns">${(cepp_investment * 2.88 * cepp_investment_unit).toLocaleString()} in savings</span>.</p>
  <p>⚡ The CEPP is the best way to meet our emission reduction goals, in line with our IPCC responsbilities.</p>
  <Chart data={cepp_data} type="line" lineOptions={fill} colors={['green', 'purple']}/>
  <p>Sources of data:</p>
  <ul>
    <li>The $150 billion clean electricity performance plan would inject $907 billion into the U.S. economy and raise $154 billion in tax revenue for federal, state, and local governments. <a href="https://www.nrdc.org/media/2021/210909">Source</a>.
      <!-- <ul>
        <li>For X drivers in the USA, that is X per year.</li>
      </ul> -->
    </li>
    <li>$150 billion in CEPP investments could <a href="https://www.evergreenaction.com/blog/the-clean-electricity-performance-program-is-key-to-delivering-on-climate">reduce Americans’ electricity bills by 5%</a>, compared to the same power sector transformation without federal grants.
      <!-- <ul>
        <li>For X drivers in the USA, that is X per year.</li>
      </ul> -->
    </li>
    <li>In 2022, the average price of electricity in the US is expected to be <a href="https://www.eia.gov/todayinenergy/detail.php?id=51438">14.26 cents/kwh</a>, and the US is expected to use <a href="https://www.eia.gov/energyexplained/electricity/use-of-electricity.php#:~:text=Electricity%20consumption%20in%20the%20United,important%20to%20the%20U.S.%20economy">3.9 trillion kilowatt hours</a>.
      <!-- <ul>
        <li>Across the USA, that is X per year.</li>
      </ul> -->
    </li>
    <li>With Americans expected to pay $556 billion in electricity costs in 2022, a 5% reduction means $27,807,000,000 in savings per year.  That is $278 billion in savings plus $154 billion in tax revnue, totaling $432 billion in returns over a ten-year period — for an investment that costs $150 billion.
      <!-- <ul>
        <li>For X drivers in the USA, that is X per year.</li>
      </ul> -->
    </li>
  </ul>
</div>

<h3><em>More coming soon ...</em></h3>
<p>Have policies to add?  Want to edit data?</p>
  <p><a href="https://docs.google.com/document/d/1w_QEqDER7GEi8Q8rOy1_RiOuT-iDZ7w20zgDESm8HSs/edit?usp=sharing">Add policies, edits, and suggestions</a>.</p>
  <hr>
  <p><a href="https://twitter.com/sambutlerUS">Twitter</p>
    <p>antiinflationary@sambutler.us</p>
</section>

<style>
  .policy {
    background: #f9f9f9;
    padding: 10px;
    border-radius: 10px;
    margin: auto;
  }

  @media only screen and (min-width: 801px) {
  .policies {
    padding: 10px;
  }
}

@media only screen and (max-width: 800px) {
  .hide-mobile {
    display: none;
  }
}

  h2 {
    margin-top: 0px;
  }

  * {
font-family: Inter var,ui-sans-serif,system-ui,-apple-system,BlinkMacSystemFont,Segoe UI,Roboto,Helvetica Neue,Arial,Noto Sans,sans-serif,Apple Color Emoji,Segoe UI Emoji,Segoe UI Symbol,Noto Color Emoji;
  }

  p, h1, h2, h3, h4, h5, h6 {
  overflow-wrap: break-word;
}

.returns {
  color: green;
}

.invested {
  color: #301bed;
}

.policy li {
  margin-bottom: 10px;
}
</style>