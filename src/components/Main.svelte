<script>
    import { onMount } from 'svelte';
  
    let fromToken = { symbol: 'ETH', amount: 0 };
    let toToken = { symbol: 'USDT', amount: 0 };
  
    async function getPrice() {
      // Fetch price for swapping
      // Update 'toToken' based on the price fetched
      toToken.amount = fromToken.amount * 2; // Example calculation, replace with actual logic
    }
  
    async function trySwap() {
      // Execute the swap logic
      console.log('Swapping:', fromToken.symbol, 'to', toToken.symbol, 'Amount:', fromToken.amount);
      // Example: send transaction to blockchain, update balances, etc.
    }
  
    onMount(() => {
      // Initialization code if needed
      getPrice(); // Fetch initial price
    });
  
    function selectFromToken(symbol) {
      fromToken.symbol = symbol;
      getPrice(); // Update price when token is changed
    }
  
    function selectToToken(symbol) {
      toToken.symbol = symbol;
      getPrice(); // Update price when token is changed
    }
  </script>
  
  <div class="flex items-center justify-center h-screen">
    <div class="bg-blue-200 text-slate-900 p-8 rounded shadow-lg">
      <h4 class="text-lg font-semibold mb-4">Trade</h4>
  
      <div class="mb-4">
        <label class="block text-sm font-bold mb-2">From Token</label>
        <div class="flex items-center">
          <select class="mr-2 form-control" bind:value={fromToken.symbol} on:change={() => selectFromToken(event.target.value)}>
            <option value="ETH">ETH</option>
            <option value="BTC">BTC</option>
            <!-- Add more options as needed -->
          </select>
          <input class="number form-control appearance-none border rounded py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline" type="number" bind:value={fromToken.amount} on:blur={getPrice}>
        </div>
      </div>
  
      <div class="mb-4">
        <label class="block text-sm font-bold mb-2">To Token</label>
        <div class="flex items-center">
          <select class="mr-2 form-control" bind:value={toToken.symbol} on:change={() => selectToToken(event.target.value)}>
            <option value="USDT">USDT</option>
            <option value="DAI">DAI</option>
            <!-- Add more options as needed -->
          </select>
          <input class="number form-control appearance-none border rounded py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline" type="number" readonly value={toToken.amount}>
        </div>
      </div>
  
      <div class="flex items-center justify-between">
        <button class="btn btn-primary" on:click={trySwap}>Swap</button>
        <button class="btn btn-secondary" on:click={getPrice}>Refresh</button>
      </div>
    </div>
  </div>
  