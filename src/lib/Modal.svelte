<script module>
  /**
   * @typedef {typeof import('svelte').SvelteComponent | typeof import('svelte').SvelteComponent<any>} Component
   * @typedef {import('svelte/types/runtime/transition').BlurParams} BlurParams
   * @typedef {import('svelte/types/runtime/transition').FadeParams} FadeParams
   * @typedef {import('svelte/types/runtime/transition').FlyParams} FlyParams
   * @typedef {import('svelte/types/runtime/transition').SlideParams} SlideParams
   * @typedef {import('svelte/types/runtime/transition').TransitionConfig} TransitionConfig
   * @typedef {Record<string, string | number>} Styles
   * @typedef {(node: Element, parameters: BlurParams | FadeParams | FlyParams | SlideParams) => TransitionConfig} TransitionFn
   * @typedef {{ id: string | null, ariaLabel: string | null, ariaLabelledBy: string | null, closeButton: Component | boolean, closeOnEsc: boolean, closeOnOuterClick: boolean, styleBg: Styles, styleWindowWrap: Styles, styleWindow: Styles, styleContent: Styles, styleCloseButton: Styles, classBg: string | null, classWindowWrap: string | null, classWindow: string | null, classContent: string | null, classCloseButton: string | null, transitionBg: TransitionFn, transitionBgProps: BlurParams, transitionWindow: TransitionFn, transitionWindowProps: BlurParams, disableFocusTrap: boolean, isTabbable: boolean, unstyled: boolean }} Options
   * @typedef {() => void} Callback
   * @typedef {{ onOpen: Callback; onOpened: Callback; onClose: Callback; onClosed: Callback }} Callbacks
   * @typedef {(NewComponent: Component, newProps?: Record<string, any>, options?: Partial<Options>, callbacks?: Partial<Callbacks>) => void} Open
   * @typedef {(callback?: Partial<Callbacks>) => void} Close
   * @typedef {{ open: Open, close: Close }} Context
   */
  
  /**
   * Create a Svelte component with props bound to it.
   * @type {(component: Component, props: Record<string, any>) => Component}
   */
  export function bind(Component, props = {}) {
    return function ModalComponent(anchor, props2) {
     return Component(
              anchor,
             {
                 ...props,
                 ...props2,
      });
    }; 
  }
  </script>
  
  <!-- svelte-ignore script_context_deprecated -->
  <script>
  import * as svelte from 'svelte';
  import { fade } from 'svelte/transition';
  
  const baseSetContext = svelte.setContext;
  
  const baseIsTabbable = (node) => {
    node.tabIndex >= 0 &&
    !node.hidden &&
    !node.disabled &&
    node.style.display !== 'none' &&
    node.type !== 'hidden' &&
    Boolean(
      node.offsetWidth || node.offsetHeight || node.getClientRects().length
    );
  }
  
  
  let {
    children,
    show = null,
    id = null,
    key = 'simple-modal',
    isTabbable = baseIsTabbable,
    ariaLabel = null,
    ariaLabelledBy = null,
    closeButton = true,
    closeOnEsc = true,
    closeOnOuterClick = true,
    styleBg = {},
    styleWindow = {},
    styleContent = {},
    styleCloseButton = {},
    styleWindowWrap = {},
    classBg = null,
    classWindowWrap = null,
    classWindow = null,
    classContent = null,
    classCloseButton = null,
    unstyled = false,
    setContext = baseSetContext,
    transitionBg = fade,
    transitionBgProps = { duration: 200 },
    transitionWindow = transitionBg,
    transitionWindowProps = transitionBgProps,
    disableFocusTrap = false
  } = $props();
  
  /**
   * A basic function that checks if a node is tabbale
   */
  
  /**
   * A function to determine if an HTML element is tabbable
   * @type {((node: Element) => boolean)}
   */
  //export let isTabbable = baseIsTabbable;
  //let isTabbable = baseIsTabbable;
  
  /**
   * Svelte component to be shown as the modal
   * @type {Component | null}
   */
  //export let show = null;
  //let show = $state(null);
  
  /**
   * Element ID assigned to the modal's root DOM element
   * @type {string | null}
   */
  //export let id = null;
  //let id = $state(null);
  
  /**
   * Svelte context key to reference the simple modal context
   * @type {string}
   */
  //export let key = 'simple-modal';
  //let key = $state('simple-modal');
  
  /**
   * Accessibility label of the modal
   * @see https://www.w3.org/TR/wai-aria-1.1/#aria-label
   * @type {string | null}
   */
  //export let ariaLabel = null;
  // let ariaLabel = $state(null);
  
  /**
   * Element ID holding the accessibility label of the modal
   * @see https://www.w3.org/TR/wai-aria-1.1/#aria-labelledby
   * @type {string | null}
   */
  //export let ariaLabelledBy = null;
  // let ariaLabelledBy = $state(null);
  
  /**
   * Whether to show a close button or not
   * @type {Component | boolean}
   */
  //export let closeButton = true;
  //let closeButton = $state(true);
  
  /**
   * Whether to close the modal on hitting the escape key or not
   * @type {boolean}
   */
  //export let closeOnEsc = true;
  //let closeOnEsc = $state(true);
  
  /**
   * Whether to close the modal upon an outside mouse click or not
   * @type {boolean}
   */
  //export let closeOnOuterClick = true;
  //let closeOnOuterClick = $state(true);
  
  /**
   * CSS for styling the background element
   * @type {Styles}
   */
  //export let styleBg = {};
  //let styleBg = $state({});
  
  /**
   * CSS for styling the window wrapper element
   * @type {Styles}
   */
  //export let styleWindowWrap = {};
  //let styleWindowWrap = $state({});
  
  /**
   * CSS for styling the window element
   * @type {Styles}
   */
  //export let styleWindow = {};
  //let styleWindow = $state({});
  
  /**
   * CSS for styling the content element
   * @type {Styles}
   */
  //export let styleContent = {};
  //let styleContent = $state({});
  
  /**
   * CSS for styling the close element
   * @type {Styles}
   */
  //export let styleCloseButton = {};
  // let styleCloseButton = $state({});
  
  /**
   * Class name for the background element
   * @type {string | null}
   */
  //export let classBg = null;
  //let classBg = $state(null);
  
  /**
   * Class name for window wrapper element
   * @type {string | null}
   */
  //export let classWindowWrap = null;
  //let classWindowWrap = $state(null);
  
  /**
   * Class name for window element
   * @type {string | null}
   */
  //export let classWindow = null;
  //let classWindow = $state(null);
  
  /**
   * Class name for content element
   * @type {string | null}
   */
  //export let classContent = null;
  //let classContent = $state(null);
  
  /**
   * Class name for close element
   * @type {string | null}
   */
  //export let classCloseButton = null;
  //let classCloseButton = $state(null);
  
  /**
   * Do not apply default styles to the modal
   * @type {boolean}
   */
  //export let unstyled = false;
  //let unstyled = $state(false);
  
  /**
   * The setContext() function associated with this library
   * @description If you want to bundle simple-modal with its own version of
   * Svelte you have to pass `setContext()` from your main app to simple-modal
   * using this parameter
   * @see https://svelte.dev/docs#run-time-svelte-setcontext
   * @type {<T>(key: any, context: T) => T}
   */
  //export let setContext = baseSetContext;
  //let setContext = $state(baseSetContext);
  
  /**
   * Transition function for the background element
   * @see https://svelte.dev/docs#transition_fn
   * @type {TransitionFn}
   */
  //export let transitionBg = fade;
  //let transitionBg = $state(fade);
  
  /**
   * Parameters for the background element transition
   * @type {BlurParams | FadeParams | FlyParams | SlideParams}
   */
  //export let transitionBgProps = { duration: 250 };
  //let transitionBgProps = $state({ duration: 250 });
  
  /**
   * Transition function for the window element
   * @see https://svelte.dev/docs#transition_fn
   * @type {TransitionFn}
   */
  //export let transitionWindow = transitionBg;
  //let transitionWindow = $state(transitionBg);
  
  /**
   * Parameters for the window element transition
   * @type {BlurParams | FadeParams | FlyParams | SlideParams}
   */
  //export let transitionWindowProps = transitionBgProps;
  //let transitionWindowProps = $state(transitionBgProps);
  
  /**
   * If `true` elements outside the modal can be focused
   * @type {boolean}
   */
  //export let disableFocusTrap = false;
  //let disableFocusTrap = $state(false);
  
  
  const defaultState = {
    id,
    ariaLabel,
    ariaLabelledBy,
    closeButton,
    closeOnEsc,
    closeOnOuterClick,
    styleBg,
    styleWindowWrap,
    styleWindow,
    styleContent,
    styleCloseButton,
    classBg,
    classWindowWrap,
    classWindow,
    classContent,
    classCloseButton,
    transitionBg,
    transitionBgProps,
    transitionWindow,
    transitionWindowProps,
    disableFocusTrap,
    isTabbable,
    unstyled,
  };
  
  
  let modalState = $state(defaultState);;
  let Component = $state(null);
  let background = $state(null);
  let wrap  = $state(null);
  let modalWindow = $state(null);
  let scrollY = $state(null);
  let cssBg = $state(null);
  let cssWindowWrap = $state(null);
  let cssWindow = $state(null);
  let cssContent = $state(null);
  let cssCloseButton = $state(null);
  let currentTransitionBg = $state(null);
  let currentTransitionWindow = $state(null);
  let prevBodyPosition = $state(null);
  let prevBodyOverflow = $state(null);
  let prevBodyWidth = $state(null);
  let outerClickTarget = $state(null);
  
  const camelCaseToDash = (str) =>
    str.replace(/([a-zA-Z])(?=[A-Z])/g, '$1-').toLowerCase();
  
  const toCssString = (props) =>
    props
      ? Object.keys(props).reduce(
          (str, key) => `${str}; ${camelCaseToDash(key)}: ${props[key]}`,
          ''
        )
      : '';
  
  const isFunction = (f) => !!(f && f.constructor && f.call && f.apply);
  
  const updateStyleTransition = () => {
    cssBg = toCssString(
      Object.assign(
        {},
        {
          width: window.innerWidth,
          height: window.innerHeight,
        },
        modalState.styleBg
      )
    );
    cssWindowWrap = toCssString(modalState.styleWindowWrap);
    cssWindow = toCssString(modalState.styleWindow);
    cssContent = toCssString(modalState.styleContent);
    cssCloseButton = toCssString(modalState.styleCloseButton);
    currentTransitionBg = modalState.transitionBg;
    currentTransitionWindow = modalState.transitionWindow;
  };
  
  const toVoid = () => {};
  let onOpen = $state(toVoid);
  let onClose = $state(toVoid);
  let onOpened = $state(toVoid);
  let onClosed = $state(toVoid);
  let targetObj = $state(null);
  /**
   * Open a modal.
   * @description Calling this method will close the modal. Additionally, it
   * allows to specify onClose and onClosed event handlers.`
   * @type {Open}
   */
  const open = (NewComponent, newProps = {}, options = {}, callbacks = {}) => {
    Component = bind(NewComponent, newProps);
    modalState = { ...defaultState, ...options };
    updateStyleTransition();
    disableScroll();
    
    if(event?.target){
      event?.target?.blur();
    }
  
    onOpen = (event) => {
      if (callbacks.onOpen) callbacks.onOpen(event);
    };
    onClose = (event) => {
      if (callbacks.onClose) callbacks.onClose(event);
    };
    onOpened = (event) => {
      if (callbacks.onOpened) callbacks.onOpened(event);
    };
    onClosed = (event) => {
      if (callbacks.onClosed) callbacks.onClosed(event);
    };
  };
  
const openOutside = (NewComponent, newProps = {}, options = {}, callbacks = {}) => {
  //Component = bind(NewComponent, newProps);
  Component = NewComponent;
  //modalState = { ...defaultState, ...options };
  updateStyleTransition();
  disableScroll();

};
  /**
   * Close the modal.
   * @description Calling this method will close the modal. Additionally, it
   * allows to specify onClose and onClosed event handlers.`
   * @type {Close}
   */
  const close = (callbacks = {}) => {
    if (!Component) return;
  
    onClose = callbacks.onClose || onClose;
    onClosed = callbacks.onClosed || onClosed;
    Component = null;
    show = null;
    enableScroll();
  };
  
  const handleKeydown = (event) => {
    if (modalState.closeOnEsc && Component && event.key === 'Escape') {
      event.preventDefault();
      close();
    }
  
    if (Component && event.key === 'Tab' && !modalState.disableFocusTrap) {
      // trap focus
      const nodes = modalWindow.querySelectorAll('*');
      const tabbable = Array.from(nodes)
        .filter(modalState.isTabbable)
        .sort((a, b) => a.tabIndex - b.tabIndex);
  
      let index = tabbable.indexOf(document.activeElement);
      if (index === -1 && event.shiftKey) index = 0;
  
      index += tabbable.length + (event.shiftKey ? -1 : 1);
      index %= tabbable.length;
  
      if(tabbable[index]){
        tabbable[index].focus();
      }
    }
  };
  
  const handleOuterMousedown = (event) => {
    if (
      modalState.closeOnOuterClick &&
      (event.target === background || event.target === wrap)
    )
      outerClickTarget = event.target;
  };
  
  const handleOuterMouseup = (event) => {
    if (modalState.closeOnOuterClick && event.target === outerClickTarget) {
      event.preventDefault();
      close();
    }
  };
  
  const disableScroll = () => {
    scrollY = window.scrollY;
    prevBodyPosition = document.body.style.position;
    prevBodyOverflow = document.body.style.overflow;
    prevBodyWidth = document.body.style.width;
    document.body.style.position = 'fixed';
    document.body.style.top = `-${scrollY}px`;
    document.body.style.overflow = 'hidden';
    document.body.style.width = '100%';
  };
  
  const enableScroll = () => {
    document.body.style.position = prevBodyPosition || '';
    document.body.style.top = '';
    document.body.style.overflow = prevBodyOverflow || '';
    document.body.style.width = prevBodyWidth || '';
    window.scrollTo({
      top: scrollY,
      left: 0,
      behavior: 'instant',
    });
  };
  
  /**
   * The exposed context methods: open() and close()
   * @type {Context}
   */
  const context = { open, close };
  
  setContext(key, context);
  
  //let isMounted = false;
  let isMounted = $state(false);
  
  svelte.onMount(() => {
    isMounted = true;
  });
    
    const openModal = () => {
      if (isMounted == false && show) {
        if (isFunction(show)) {
          open(show);
        } else {
          close();
        
        }
      }
    }
  
  $effect(() => {
  //For outside
      if (isFunction(show)  && show) {
        openOutside(show);
      }
  });
  
    $effect(() => {
    //For open Funtion
      if (isMounted == false && show) {
        if (isFunction(show)) {
          open(show);
        } else {
          close();
        
        }
      }
      return () => {
         if (isMounted) close();
        
         isMounted = false;
         modalWindow = null;
         Component = null;
      }
    });
  
     $effect(()=>{
        if (Component && modalWindow) {
        // trap focus
          const nodes = modalWindow.querySelectorAll('*');
          const tabbable = Array.from(nodes)
            .filter(modalState.isTabbable)
            .sort((a, b) => a.tabIndex - b.tabIndex);
  
          let index = tabbable.indexOf(document.activeElement);
          if (index === -1 && event?.shiftKey) index = 0;
  
          index += tabbable.length + (event?.shiftKey ? -1 : 1);
          index %= tabbable.length;
  
          tabbable[index].focus();
      }
     })
  </script>
  
  <svelte:window onkeydown={handleKeydown} />
  
  {#if Component}
  <div 
    aria-hidden="true"
    id={modalState.id}
    class={modalState.classBg}
    class:bg={!unstyled}
    onmousedown={handleOuterMousedown}
    onmouseup={handleOuterMouseup}
    bind:this={background}
    transition:currentTransitionBg={modalState.transitionBgProps}
    style={cssBg}
  >
    <div
      class={modalState.classWindowWrap}
      class:wrap={!unstyled}
      bind:this={wrap}
      style={cssWindowWrap}
    >
      <div
        class={modalState.classWindow}
        class:window={!unstyled}
        role="dialog"
        tabindex='-1'
        aria-modal="true"
        aria-label={modalState.ariaLabelledBy ? null : modalState.ariaLabel || null}
        aria-labelledby={modalState.ariaLabelledBy || null}
        bind:this={modalWindow}
        transition:currentTransitionWindow={modalState.transitionWindowProps}
        onintrostart={onOpen}
        onoutrostart={onClose}
        onintroend={onOpened}
        onoutroend={onClosed}
        style={cssWindow}
      >
        {#if modalState.closeButton}
          {#if isFunction(modalState.closeButton)}
            <!-- <svelte:component this={modalState.closeButton} onClose={close} /> -->
            <button bind:this={modalState.closeButton} onClose={close}>X</button>
          {:else}
            <button
              class={modalState.classCloseButton}
              class:close={!unstyled}
              aria-label="Close modal"
              onclick={close}
              style={cssCloseButton}
              type="button"
            ></button>
          {/if}
        {/if}
        <div
          class={modalState.classContent}
          class:content={!unstyled}
          style={cssContent}
        >
          <!-- <svelte:component this={Component} /> -->
          <Component />
        </div>
      </div>
    </div>
  </div>
  {/if}
  <!-- <slot /> -->
  {@render children?.()}
  
  <style>
  * {
    box-sizing: border-box;
  }
  
  .bg {
    position: fixed;
    z-index: 1005;
    top: 0;
    left: 0;
    display: flex;
    flex-direction: column;
    justify-content: center;
    width: 100vw;
    height: 100vh;
    background: rgba(0, 0, 0, 0.66);
  }
  
  .wrap {
    position: relative;
    margin: 2rem;
    max-height: 100%;
  }
  
  .window {
    position: relative;
    width: 40rem;
    max-width: 100%;
    max-height: 100%;
    margin: 2rem auto;
    color: black;
    border-radius: 0.5rem;
    background: white;
  }
  
  .content {
    position: relative;
    padding: 1rem;
    max-height: calc(100vh - 4rem);
    overflow: auto;
  }
  
  .close {
    display: block;
    box-sizing: border-box;
    position: absolute;
    z-index: 1000;
    top: 1rem;
    right: 1rem;
    margin: 0;
    padding: 0;
    width: 1.5rem;
    height: 1.5rem;
    border: 0;
    color: black;
    border-radius: 1.5rem;
    background: white;
    box-shadow: 0 0 0 1px black;
    transition: transform 0.2s cubic-bezier(0.25, 0.1, 0.25, 1),
      background 0.2s cubic-bezier(0.25, 0.1, 0.25, 1);
    -webkit-appearance: none;
  }
  
  .close:before,
  .close:after {
    content: '';
    display: block;
    box-sizing: border-box;
    position: absolute;
    top: 50%;
    width: 1rem;
    height: 1px;
    background: black;
    transform-origin: center;
    transition: height 0.2s cubic-bezier(0.25, 0.1, 0.25, 1),
      background 0.2s cubic-bezier(0.25, 0.1, 0.25, 1);
  }
  
  .close:before {
    -webkit-transform: translate(0, -50%) rotate(45deg);
    -moz-transform: translate(0, -50%) rotate(45deg);
    transform: translate(0, -50%) rotate(45deg);
    left: 0.25rem;
  }
  
  .close:after {
    -webkit-transform: translate(0, -50%) rotate(-45deg);
    -moz-transform: translate(0, -50%) rotate(-45deg);
    transform: translate(0, -50%) rotate(-45deg);
    left: 0.25rem;
  }
  
  .close:hover {
    background: black;
  }
  
  .close:hover:before,
  .close:hover:after {
    height: 2px;
    background: white;
  }
  
  .close:active {
    transform: scale(0.9);
  }
  
  .close:hover,
  .close:focus,
  .close:active {
    outline: none;
  }
  </style>