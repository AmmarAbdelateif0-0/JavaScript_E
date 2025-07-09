
```js
document.addEventListener('keydown', function (e) {

  if (e.key == 'Escape' && !modal.classList.contains('hidden')) {
    closeModal();
  }
});
```

* Read this : https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/key#value



