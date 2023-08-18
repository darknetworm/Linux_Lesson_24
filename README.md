# Linux_Lesson_24
Collection and analysis of logs

Лабораторный стенд для сбора и анализа логов, настраиваемый с использованием Vagrant и Ansible. Все файлы и структуру директории roles необходимо скопировать в одну директорию.

Vagrantfile - автоматизированно создает, настраивает с помощью Ansible веб-сервер и сервер сбора логов.

ansible.cfg - файл конфигурации для доступа playbook к серверу.

hosts - файл с настройками групп серверов для быстрого доступа к ним из playbook.

main.yml - основной файл playbook для установки и настройки необходимых компонентов каждого из серверов. Содержит предварительные общие задачи по синхронизации времени на серверах и задачи для каждого сервера отдельно: для сервера сбора логов - установка и настройка сервисов rsyslog и auditd; для вуб-сервера - установка nginx из epel и настройка его для отправки логов на удаленный сервер.

Директория roles содержит задачи из основного файла playbook по установке из репозиториев требуемых модулей, изменению конфигурационных файлов сервисов и их перезапуску.
