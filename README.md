<div style="font-family: Arial, sans-serif; font-size: 14px; line-height: 1.6; color: #333; max-width: 800px; margin: 0 auto;">

<h1 align="center" style="color: #2c3e50; border-bottom: 2px solid #3498db; padding-bottom: 10px;">«УП.04 Сопровождение и обслуживание программного обеспечения компьютерных систем» </h1>
<h2 style="color: #3498db;">Неделя 02</h2>

<div style="background-color: #f8f9fa; padding: 15px; border-radius: 5px; margin-bottom: 20px;">
<h3 style="color: #2c3e50; margin-top: 0;">День 1. Первичная установка и настройка Zabbix</h3>

<ol>
<h4 style="color: #3498db;">1. В VM VirtualBox установить и правильно настроить ОС РЕД ОС, создать пользователя <code>user/user</code> (логин/пароль)</h4>
<h4 style="color: #3498db;">2. Выполнить настройку сервера на MySQL и Zabbix 6.4 с помощью <a href="https://redos.red-soft.ru/base/redos-8_0/8_0-administation/8_0-monitoring/8_0-zabbix/8_0-zabbix64-mysql/" target="_blank">официальной инструкции:</h4>
    <ul>
    <li>Предварительная подготовка сервера</li>
    <li>Настройка сервера на MySQL</li>
    <li>Настройка базы данных</li>
    <li>Запуск процесса Zabbix-сервера</li>
    <li>Настройка из веб-интерфейса</li>
    </ul>
</li>
<h4 style="color: #3498db;">3. Выполнить настройку и добавление <a href="https://www.zabbix.com/documentation/6.4/ru/manual/concepts/agent" target="_blank">Zabbix Agent</a></h4>
</ol>
</div>

<div style="background-color: #f8f9fa; padding: 15px; border-radius: 5px; margin-bottom: 20px;">
<h3 style="color: #2c3e50; margin-top: 0;">День 2. Агентный мониторинг ОС Windows</h3>

<ol>
<h4 style="color: #3498db;">1. Подготовка</h4>
<p>В качестве объекта мониторинга будет использована ОС Windows, установленная на виртуальной машине и введенная в домен.</p>

<h4 style="color: #3498db;">2. Установка агента</h4>
<p>Скачать <a href="https://cdn.zabbix.com/zabbix/binaries/stable/6.4/6.4.21/" target="_blank">исходный код агента</a> с официального сайта проекта и установить Zabbix Agent в ОС Windows.</p>

<h4 style="color: #3498db;">3. Создание узла сети</h4>
<ol>
<li>Создать группу узлов сети <strong>Agent Monitoring Servers</strong></li>
<li>Создать узел сети <code>[fam_stud].local</code></li>
<li>Установить параметр «Автоматически» для инвентарных данных</li>
<li>Создать и настроить шаблон опроса <strong>Agent Windows Monitor</strong>:
    <ul>
    <li>Заполнить элементами данных (см. таблицу 1)</li>
    <li>Выполнить сбор инвентарных данных</li>
    </ul>
</li>
<li>Создать триггеры</li>
<li>Создать графики и проанализировать результаты</li>
</ol>

<h4 style="color: #3498db;">4. Низкоуровневое обнаружение</h4>
<ol>
<li>Создать правило обнаружения сетевых интерфейсов</li>
<li>Создать прототипы элементов данных для подсчета трафика</li>
<li>Создать 2 прототипа графиков:
    <ul>
    <li>Загрузка интерфейсов трафиком</li>
    <li>Ошибки на интерфейсах</li>
    </ul>
</li>
<li>Создать и настроить фильтр регулярных выражений</li>
<li>Создать обнаружение для мониторинга дискового пространства</li>
<li>Просмотреть результаты через Комплексный экран</li>
</ol>
</div>

<div style="background-color: #f8f9fa; padding: 15px; border-radius: 5px; margin-bottom: 20px;">
</ol>
<h3 style="color: #2c3e50; margin-top: 0;">День 3. Агентный мониторинг ОС Linux</h3>

<h4 style="color: #3498db;">1. Подготовка</h4>
<p>Объект мониторинга - виртуальная машина с ОС РЕД ОС и установленным Zabbix-сервером.</p>

<h4 style="color: #3498db;">2. Установка агента</h4>
<p>Установить Zabbix Agent (если не установлен).</p>

<h4 style="color: #3498db;">3. Создание узла сети</h4>
<ol>
<li>Создать шаблон опроса <strong>Agent Linux Monitor</strong></li>
<li>Создать узел сети <code>[fam_stud].linux.home</code> (IP: 127.0.0.1)</li>
<li>Заполнить шаблон элементами данных, триггерами и графиками</li>
<li>Создать триггеры</li>
<li>Настроить низкоуровневое обнаружение:
    <ul>
    <li>Жесткие диски</li>
    <li>Сетевые интерфейсы</li>
    </ul>
</li>
<li>Создать фильтр для исключения букв алфавита</li>
<li>Просмотреть результаты через Комплексный экран</li>
</ol>
</div>

<div style="text-align: center; margin-top: 30px; font-style: italic; color: #7f8c8d;">
<p>Материал подготовлен для учебной практики </p>
<p>2024-2025</p>
</div>

</div>
