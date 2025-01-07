```css
@keyframes fadeInUp{
	0% {
    opacity: 0;
    transform: translate3d(0 , 100% , 0);
}
	100% {
    opacity: 1;
    transform: none;
}
}

.element{
	animation-duration: 1.25s;
  animation-name: fadeInUp;
}
