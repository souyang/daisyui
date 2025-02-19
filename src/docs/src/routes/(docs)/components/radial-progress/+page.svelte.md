---
title: Radial progress
desc: Radial progress can be used to show the progress of a task or to show the passing of time.
published: true
layout: components
---

<script>
  import Component from "$components/Component.svelte"
  import ClassTable from "$components/ClassTable.svelte"
  import ComponentPageTabs from "$components/ComponentPageTabs.svelte"
  import BrowserSupport from "$components/BrowserSupport.svelte"
  import Translate from "$components/Translate.svelte"
  import { prefix } from '$lib/stores';
  import { replace } from '$lib/actions';
</script>

<Translate text="Radial progress needs `--value` CSS variable to work.<br />To change the size, use `--size` CSS variable which has a default value of `4rem`.<br />To change the thickness, use `--thickness` CSS variable which is 10% of the size by default.<br />" />

<div class="alert alert-info text-sm mt-2">
  <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" class="stroke-info-content shrink-0 w-6 h-6"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 16h-1v-4h-1m1-4h.01M21 12a9 9 0 11-18 0 9 9 0 0118 0z"></path></svg>
  For radial progress we use &lt;div&gt; instead of &lt;progress&gt; tag because Browsers are unable to show the text inside &lt;progress&gt; tag and Firefox doesn't show the pseudo elements inside &lt;progress&gt; bar at all.
  For accessibility, a role of 'progressbar' is given to each &lt;div&gt; explicitly, while 
  &lt;progress&gt; receives this role implicitly.
</div>

<!-- <ComponentPageTabs/> -->

<ClassTable
data="{[
  { type:'component', class: 'radial-progress', desc: 'Shows a radial progress' },
]}"
/>

<Component title="Radial progress">
<div class="radial-progress" style="--value:70;" role="progressbar">70%</div>
<pre slot="html" use:replace={{ to: $prefix }}>{
`<div class="$$radial-progress" style="--value:70;" role="progressbar">70%</div>`
}</pre>
<pre slot="jsx" use:replace={{ to: $prefix }}>{
`<div className="$$radial-progress" style={{"--value":70}} role="progressbar">70%</div>`
}</pre>
</Component>

<Component title="Different values">
<div class="radial-progress" style="--value:0;" role="progressbar">0%</div>
<div class="radial-progress" style="--value:20;" role="progressbar">20%</div>
<div class="radial-progress" style="--value:60;" role="progressbar">60%</div>
<div class="radial-progress" style="--value:80;" role="progressbar">80%</div>
<div class="radial-progress" style="--value:100;" role="progressbar">100%</div>
<pre slot="html" use:replace={{ to: $prefix }}>{
`<div class="$$radial-progress" style="--value:0;" role="progressbar">0%</div>
<div class="$$radial-progress" style="--value:20;" role="progressbar">20%</div>
<div class="$$radial-progress" style="--value:60;" role="progressbar">60%</div>
<div class="$$radial-progress" style="--value:80;" role="progressbar">80%</div>
<div class="$$radial-progress" style="--value:100;" role="progressbar">100%</div>`
}</pre>
<pre slot="jsx" use:replace={{ to: $prefix }}>{
`<div className="$$radial-progress" style={{"--value":0}} role="progressbar">0%</div>
<div className="$$radial-progress" style={{"--value":20}} role="progressbar">20%</div>
<div className="$$radial-progress" style={{"--value":60}} role="progressbar">60%</div>
<div className="$$radial-progress" style={{"--value":80}} role="progressbar">80%</div>
<div className="$$radial-progress" style={{"--value":100}} role="progressbar">100%</div>`
}</pre>
</Component>

<Component title="Custom color">
<div class="radial-progress text-primary" style="--value:70;" role="progressbar">70%</div>
<pre slot="html" use:replace={{ to: $prefix }}>{
`<div class="$$radial-progress text-primary" style="--value:70;" role="progressbar">70%</div>`
}</pre>
<pre slot="jsx" use:replace={{ to: $prefix }}>{
`<div className="$$radial-progress text-primary" style={{"--value":70}} role="progressbar">70%</div>`
}</pre>
</Component>

<Component title="With background color and border">
<div class="radial-progress bg-primary text-primary-content border-4 border-primary" style="--value:70;" role="progressbar">70%</div>
<pre slot="html" use:replace={{ to: $prefix }}>{
`<div class="$$radial-progress bg-primary text-primary-content border-4 border-primary" style="--value:70;" role="progressbar">70%</div>`
}</pre>
<pre slot="jsx" use:replace={{ to: $prefix }}>{
`<div className="$$radial-progress bg-primary text-primary-content border-4 border-primary" style={{"--value":70}} role="progressbar">70%</div>`
}</pre>
</Component>

<Component title="Custom size and custom thickness">
<div class="radial-progress" style="--value:70; --size:12rem; --thickness: 2px;" role="progressbar">70%</div>
<div class="radial-progress" style="--value:70; --size:12rem; --thickness: 2rem;" role="progressbar">70%</div>
<pre slot="html" use:replace={{ to: $prefix }}>{
`<div class="$$radial-progress" style="--value:70; --size:12rem; --thickness: 2px;" role="progressbar">70%</div>
<div class="$$radial-progress" style="--value:70; --size:12rem; --thickness: 2rem;" role="progressbar">70%</div>`
}</pre>
<pre slot="jsx" use:replace={{ to: $prefix }}>{
`<div className="$$radial-progress" style={{ "--value": "70", "--size": "12rem", "--thickness": "2px" }} role="progressbar">70%</div>
<div className="$$radial-progress" style={{ "--value": "70", "--size": "12rem", "--thickness": "2rem" }} role="progressbar">70%</div>`
}</pre>
</Component>
