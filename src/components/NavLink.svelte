    
<script>
  import { Link } from "svelte-routing";
  export let to = "";
  export let className = '';
  
  function getProps({ location, href, isPartiallyCurrent, isCurrent }) {
    const isActive = href === "/" ? isCurrent : isPartiallyCurrent || isCurrent;
    // The object returned here is spread on the anchor element's attributes
    if (isActive) {
      return { class: "active " + className };
    }
    return {
        class: className
    };
  }
</script>

<Link to="{to}" getProps="{getProps}">
  <slot />
</Link>