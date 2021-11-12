### detect browser out event in React.js

```
    useEffect(() => {
    const handleBrowserOut = (e) => {
      e.preventDefault();
      var confirmationMessage = "o/";

      (e || window.event).returnValue = confirmationMessage; //Gecko + IE
      return confirmationMessage;
    };
    window.addEventListener("beforeunload", (e) => handleBrowserOut(e));
    return () => {
      window.removeEventListener("beforeunload", (e) => handleBrowserOut(e));
    };
  }, []);

```
