# useful-hooks

## useMediaQuery()

The hook is originally from [usehooks-ts](https://usehooks-ts.com/react-hook/use-media-query) but updated to resolve the hydration issue.
To check viewport dimensions and also used by the useDarkMode() hook

## useDarkMode()

Also from [usehooks-ts](https://usehooks-ts.com/react-hook/use-dark-mode) but since the original depends upon other hooks, it has been simplified to work with useMediaQuery() hook only and TailwindCSS.
The hook toggles the 'dark' class for TailwindCSS. Also added support for system mode rather than toggling between light and dark mode.

##useClickOutside()

A hook to detect the mouse button down outside the referenced element. Applicable for closing dropdown menus when the mouse is clicked anywhere outside the menu.

### Usage
```jsx
import { useClickOutside } from "/useClickOutside";

export default function Component() {
  const [open, setOpen] = useState(false);

    const menuRef = useClickOutside(() => {
    setOpen(false);
    });
    return(
        <button
        className="relative text-xl p-4 mx-2 flex items-center gap-2"
        onClick={() => setOpen(!open)}
        ref={menuRef}>
            {children}
        </button>
    )
}
```
