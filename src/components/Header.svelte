<script>
    let tabs = [
      { name: 'Swap', link: '#swap' },
      { name: 'Token', link: '#token' },
      { name: 'Connect Wallet', link: '#wallet' },
    ];
  
    
  </script>
  
  <header class=" text-white p-4">
    <div class="container mx-auto flex justify-between items-center">
      <div class="text-2xl font-bold">
        <h1
          class="font-bold text-transparent bg-gradient-to-r bg-clip-text from-slate-900 to-green-500"
        >
          <b>XX</b>swap
        </h1>
      </div>
  

  
        <nav class="flex items-center">
          <ul class="flex space-x-4">
            {#each tabs as tab}
              <li>
                <a
                  href={tab.link}
                  class="relative overflow-hidden px-5 py-2 group rounded-full bg-white hover:scale-150
                      text-green-700 hover:text-slate-950 transition-colors duration-200">{tab.name}</a
                >
              </li>
            {/each}
          </ul>
        </nav>
      </div>
  </header>
  