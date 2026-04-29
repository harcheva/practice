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
    <ul>
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
    </ul>

<h4 style="color: #3498db;">4. Низкоуровневое обнаружение</h4>
    <ul>
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
    </ul>
</div>

<div style="background-color: #f8f9fa; padding: 15px; border-radius: 5px; margin-bottom: 20px;">
</ol>
<h3 style="color: #2c3e50; margin-top: 0;">День 3. Агентный мониторинг ОС Linux</h3>

<ol>
<h4 style="color: #3498db;">1. Подготовка</h4>
<p>Объект мониторинга - виртуальная машина с ОС РЕД ОС и установленным Zabbix-сервером.</p>

<h4 style="color: #3498db;">2. Установка агента</h4>
<p>Установить Zabbix Agent (если не установлен).</p>

<h4 style="color: #3498db;">3. Создание узла сети</h4>
    <ul>
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
    </ul>
</ol>
</div>


<div style="font-family: Arial, sans-serif; font-size: 14px; line-height: 1.6; color: #333; max-width: 800px; margin: 0 auto;">

<div style="background-color: #f8f9fa; padding: 15px; border-radius: 5px; margin-bottom: 20px;">
<h3 style="color: #2c3e50; margin-top: 0;">День 4. Мониторинг MySQL через Zabbix-агент и внешний скрипт (Bash)</h3>

<ol>
<li><strong>Настройка Zabbix-агента для доступа к MySQL</strong>
    <ul>
    <li>Проверить <code>/etc/zabbix/zabbix_agentd.conf</code>: строка <code>Include=/etc/zabbix/zabbix_agentd.d/*.conf</code></li>
    <li>Создать <code>/var/lib/zabbix/.my.cnf</code>:</li>
    </ul>
    <pre>[client]
user = agent
password = agent</pre>
    <ul><li>Перезапустить агента: <code>sudo systemctl restart zabbix-agent</code></li></ul>
</li>

<li><strong>Создание пользователя MySQL для мониторинга</strong>
    <ul>
    <li><code>mysql -uroot -proot</code></li>
    <li><code>CREATE USER 'agent'@'localhost' IDENTIFIED BY 'agent';</code></li>
    <li><code>GRANT SELECT ON *.* TO 'agent'@'localhost';</code></li>
    <li><code>FLUSH PRIVILEGES;</code></li>
    </ul>
</li>

<li><strong>Создание шаблона и узла сети</strong>
    <ul>
    <li>Шаблон: <strong>User MySQL Monitor</strong> (группа User Templates)</li>
    <li>Узел: <code>[fam_stud].mysql.home</code> (IP 127.0.0.1), группа Agent Monitoring Servers</li>
    <li>Присоединить шаблон к узлу</li>
    </ul>
</li>

<li><strong>Элементы данных (Zabbix-агент)</strong>
    <ul>
    <li><code>mysql.ping</code> — доступность БД (30 сек)</li>
    <li><code>mysql.version</code> — версия (1 час)</li>
    <li><code>mysql.status[Uptime]</code> — время работы (60 сек)</li>
    <li><code>mysql.status[Queries]</code> — кол-во запросов (60 сек)</li>
    <li><code>mysql.status[Slow_queries]</code> — медленные запросы (60 сек)</li>
    <li><code>mysql.status[Threads_connected]</code> — открыто соединений (60 сек)</li>
    </ul>
</li>

<li><strong>Триггеры</strong>
    <ul>
    <li>Недоступность MySQL: <code>{User MySQL Monitor:mysql.ping.last()}=0</code> (Высокая)</li>
    <li>Много медленных запросов: <code>{User MySQL Monitor:mysql.status[Slow_queries].min(5m)}>10</code> (Средняя)</li>
    </ul>
</li>

<li><strong>Графики</strong>
    <ul>
    <li>Активность запросов (Queries + Slow_queries)</li>
    <li>Загрузка соединений (Threads_connected)</li>
    </ul>
</li>

<li><strong>Внешний скрипт на Bash (размер БД)</strong>
    <ul>
    <li>Создать <code>/usr/lib/zabbix/externalscripts/db_size.sh</code>:</li>
    </ul>
    <pre>
#!/bin/bash
# Учётные данные
MYSQL_USER="agent"
MYSQL_PASS="agent"
MYSQL_HOST="localhost"
MYSQL_DB="zabbix"
# SQL-запрос: размер базы данных в МБ
QUERY="SELECT ROUND(SUM(data_length + index_length) / 1024 / 1024, 2) 
       FROM information_schema.TABLES 
       WHERE table_schema = 'zabbix';"
# Выполнение запроса
mysql -u"$MYSQL_USER" -p"$MYSQL_PASS" -h"$MYSQL_HOST" -N -e "$QUERY" 2>/dev/null</pre>
    <ul>
    <li>Выдать права: <code>sudo chmod +x /usr/lib/zabbix/externalscripts/db_size.sh</code></li>
    <li>Проверить вручную: <code>/usr/lib/zabbix/externalscripts/db_size.sh</code></li>
    </ul>
</li>

<li><strong>Добавление внешней проверки в шаблон</strong>
    <ul>
    <li>Элемент данных: тип <strong>Внешняя проверка</strong>, ключ <code>db_size.sh</code></li>
    <li>Тип информации: Числовой (целое), ед. изм. МБ, интервал 300 сек</li>
    <li>Триггер: размер БД > 1024 МБ</li>
    <li>График: динамика размера БД</li>
    </ul>
</li>

<li><strong>Инвентарные данные</strong> (заполнить в узле)
    <ul>
    <li>Тип устройства: СУБД</li>
    <li>ОС: <code>mysql.version</code></li>
    <li>Время работы: <code>mysql.status[Uptime]</code></li>
    <li>Размер БД: <code>db_size.sh</code></li>
    </ul>
</li>

<li><strong>Комплексный экран MySQL Dashboard</strong>
    <ul>
    <li>Все графики + индикатор доступности + список проблем</li>
    </ul>
</li>
</ol>
</div>


</div>

<div style="text-align: center; margin-top: 30px; font-style: italic; color: #7f8c8d;">
<p>Материал подготовлен для учебной практики </p>
<p>2025-2026</p>
</div>

</div>
