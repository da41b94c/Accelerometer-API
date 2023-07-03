<h1>Доступ к данным акселерометра устройства с помощью Accelerometer API</h1>
Accelerometer API позволяет веб-сайтам получать данные акселерометра и использовать их для различных целей.
Например, для определения ориентации устройства, обнаружения движений, создания интерактивных игр или прокрутки контента на веб-странице на основе движений пользователя.

![Accelerometer](https://www.w3.org/TR/accelerometer/images/accelerometer_coordinate_system.svg)

```
if ('Accelerometer' in window && typeof window.Accelerometer === 'function' )
{
	const accelerometer = new Accelerometer({ frequency: 60 });
	
	accelerometer.addEventListener('reading', () => {
 		const accelerationX = accelerometer.x;
   		const accelerationY = accelerometer.y;
	 	const accelerationZ = accelerometer.z;
   		msgElement.innerHTML += `X: ${accelerationX}, Y: ${accelerationY}, Z: ${accelerationZ}<br>`;
	 });
  
  	accelerometer.addEventListener('error', (event) => {
   		msgElement.innerHTML += `Ошибка акселерометра: ${event.error.name}<br>`;
	 });
  	accelerometer.start();
}
```

## Поддержка браузерами
На текущий момент <a href="https://caniuse.com/?search=Accelerometer">Accelerometer API поддерживается</a> в некоторых мобильных браузерах:
- Chrome для Android
- Firefox для Android
- UC Browser for Android

<div align="center">
	<a href="https://developer.donnoval.ru/accelerometer-api/">https://developer.donnoval.ru/accelerometer-api/</a>
</div>
