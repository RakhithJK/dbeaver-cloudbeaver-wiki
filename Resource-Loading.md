We are using [React Suspense](https://17.reactjs.org/docs/concurrent-mode-suspense.html) for data loading. (It's part of [Concurrent Mode](https://17.reactjs.org/docs/concurrent-mode-intro.html))<br/>

```tsx
export const ExtendedDDLViewerTabPanel: NavNodeTransformViewComponent = observer(function ExtendedDDLViewerTabPanel({
  nodeId, folderId
}) {
  const extendedDDLResource = useResource(ExtendedDDLViewerTabPanel, ExtendedDDLResource, nodeId);
  const connectionDialectResource = useResource(ExtendedDDLViewerTabPanel, ConnectionDialectResource, connectionParam);

  return styled(style)(
    <wrapper>
      <SQLCodeEditorLoader
        bindings={{
          autoCursor: false,
        }}
        value={extendedDDLResource.data}
        dialect={connectionDialectResource.data}
        readonly
      />
      <MenuBar menu={menu} style={MENU_BAR_DEFAULT_STYLES} />
    </wrapper>
  );
});
```
1. We are loading resources with `useResource`
2. when we access `extendedDDLResource.data` and `connectionDialectResource.data` it triggers `suspense` API
3. `<Loader suspense>` used in `TabPanel` will display loading states

**How it works:**<br/>
`useResource` will load data and track resource outdating. It's returning state with data and `isLoading`, `isLoaded`, `isOutdated`, `tryGetData`<br/>
`tryGetData` is equivalent to `data` but it will not trigger `suspense` API and can be used to track loading states manually<br/>
The closest `Loader` will display states of loading.

### useResource(component, resource, key)
component - can be React Component, React Functional Component or React Hook<br>
resource - resource instance or class<br>
key - null (skip resource loading) or any other valid value<br>
