<script lang="ts">
  type Props = {
    type?: 'primary' | 'secondary' | 'outline' | 'white';
    href?: string;
    className?: string;
  };
  
  let { type = 'primary', href, className = '' }: Props = $props();
</script>

{#if href}
  <a
    {href}
    class="inline-flex items-center justify-center px-6 py-3 rounded-full font-medium transition-all active:scale-95 {className}
    {type === 'primary' ? 'bg-primary-500 text-white hover:bg-primary-600 shadow-lg shadow-primary-500/20' : ''}
    {type === 'secondary' ? 'bg-[#130b29] text-white hover:bg-black' : ''}
    {type === 'outline' ? 'border border-white/20 bg-transparent text-white hover:bg-white/10' : ''}
    {type === 'white' ? 'bg-white text-[#130b29] hover:bg-gray-100' : ''}"
  >
    <slot />
  </a>
{:else}
  <button
    class="inline-flex items-center justify-center px-6 py-3 rounded-full font-medium transition-all active:scale-95 {className}
    {type === 'primary' ? 'bg-primary-500 text-white hover:bg-primary-600 shadow-lg shadow-primary-500/20' : ''}
    {type === 'secondary' ? 'bg-[#130b29] text-white hover:bg-black' : ''}
    {type === 'outline' ? 'border border-white/20 bg-transparent text-white hover:bg-white/10' : ''}
    {type === 'white' ? 'bg-white text-[#130b29] hover:bg-gray-100' : ''}"
  >
    <slot />
  </button>
{/if}
