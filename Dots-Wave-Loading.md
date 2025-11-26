

```html
 <div class="wave-loading">
         <span></span>
         <span></span>
         <span></span>
</div>
```


```css
.wave-loading {
  display: flex;
  gap: 6px;
  align-items: flex-end;
}

.wave-loading span {
  width: 8px;
  height: 8px;
  background: #333;
  border-radius: 50%;
  display: inline-block;
  animation: wave 0.6s infinite ease-in-out;
}

.wave-loading span:nth-child(2) {
  animation-delay: 0.15s;
}

.wave-loading span:nth-child(3) {
  animation-delay: 0.3s;
}

@keyframes wave {
  0%, 60%, 100% {
    transform: translateY(0);
    opacity: 1;
  }
  30% {
    transform: translateY(-8px);
    opacity: 0;   /* fade out at top */
  }
}

```
