<p>Accelerometer API позволяет веб-сайтам получать данные акселерометра и использовать их для различных целей.</p>
<p>Например, для определения ориентации устройства, обнаружения движений, создания интерактивных игр или прокрутки контента на веб-странице на основе движений пользователя.</p>
<pre>
// Проверяем поддержку Accelerometer API
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
</pre>
<p>На текущий момент <a href="https://caniuse.com/?search=Accelerometer">Accelerometer API поддерживается</a> в некоторых мобильных браузерах:</p>
<ul>
	<li><p>Chrome для Android </p></li>
	<li><p>Firefox для Android </p></li>
	<li><p>UC Browser for Android </p></li>
</ul>
<p><a href="https://developer.donnoval.ru/accelerometer-api/">https://developer.donnoval.ru/accelerometer-api/</a></p>
