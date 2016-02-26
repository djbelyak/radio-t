---
layout: page
title: "Слушать Online вещание"
date: 2012-06-13T22:53:00
comments: false
sharing: true
footer: false
---
![](/images/listen.jpg)
Запись подкаста производится по субботам, в 23:00мск. В это время, вы можете слушать нас в прямом эфире по ссылке: [http://stream.radio-t.com](http://stream.radio-t.com)

Для обратной связи: jabber чат conference.radio-t.com room: online

Так–же можно воспользоваться специальной программой [http://apps.radio-t.com](http://apps.radio-t.com) позволяющей одновременно слушать эфир, читать/писать в чат, голосовать и прочее приятное.


Обратный отсчет: <span id="timer"></span>

<script>
function setShowTimer() {
    function getUnits(value, units) {
        return (/^[0,2-9]?[1]$/.test(value)) ? units[0] : ((/^[0,2-9]?[2-4]$/.test(value)) ? units[1] : units[2])
    }

    var timeInMoscow = new Date();
    timeInMoscow.setMinutes(timeInMoscow.getMinutes() + timeInMoscow.getTimezoneOffset() + 3 * 60);

    var nextShow = new Date(timeInMoscow);
    nextShow.setDate(nextShow.getDate() + 6 - nextShow.getDay());
    nextShow.setHours(23, 0, 0, 0);

    var totalSeconds = Math.floor((nextShow - timeInMoscow) / 1000);

    if (totalSeconds < 0) {
        return "Вещаем!";
    }

    var seconds = totalSeconds % 60,
        minutes = Math.round((totalSeconds - seconds) / 60) % 60,
        hours = Math.round((totalSeconds - seconds - minutes * 60) / 3600),
        days = (hours - hours % 24) / 24;

    hours %= 24;

    var result = "",
        daysList = ['день', 'дня', 'дней'],
        hoursList = ['час', 'часа', 'часов'],
        minutesList = ['минута', 'минуты', 'минут'],
        secondsList = ['секунда', 'секунды', 'секунд'];

    if (days > 0) {
        result += days + ' ' + getUnits(days, daysList) + ' ';
    }

    result += (('0' + hours).slice(-2) + ' ' + getUnits(hours, hoursList) + ' ') + 
              (('0' + minutes).slice(-2) + ' ' + getUnits(minutes, minutesList) + ' ') + 
              (('0' + seconds).slice(-2) + ' ' + getUnits(seconds, secondsList));

    return result;
}

var t = document.getElementById('timer');

t.textContent = setShowTimer();
window.setInterval(function() {
    t.textContent = setShowTimer();
}, 999);
</script>
