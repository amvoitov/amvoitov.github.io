---
title: "Кейс 3: Весовая система для бункера перегрузчика"
permalink: /projects/case_3/
---

<a class="site_btn" href="{{ '/projects/' | relative_url }}">← Назад к проектам</a>

<div class="site_case_head">
<b>Коротко:</b> блок обработки сигнала тензодатчика + Android (отображение/фильтрация/офлайн) + портал аналитики и телеметрии.

<div class="row g-2 mt-2">
  <div class="col-12 col-sm-6 col-lg-3"><div class="site_kpi"><div class="site_kpi_label">Роль</div><div class="site_kpi_value">PM/PO/аналитик/архитектор</div></div></div>
  <div class="col-12 col-sm-6 col-lg-3"><div class="site_kpi"><div class="site_kpi_label">Период</div><div class="site_kpi_value">10.2021 → 11.2022+</div></div></div>
  <div class="col-12 col-sm-6 col-lg-3"><div class="site_kpi"><div class="site_kpi_label">Команда</div><div class="site_kpi_value">7+ участников</div></div></div>
  <div class="col-12 col-sm-6 col-lg-3"><div class="site_kpi"><div class="site_kpi_label">Эффект</div><div class="site_kpi_value">−70% потерь</div></div></div>
</div>

<div class="d-flex flex-wrap gap-2 mt-3">
  <button type="button" class="btn btn-outline-primary btn-sm" data-bs-toggle="modal" data-bs-target="#case3Artifacts">
    Артефакты (что могу показать)
  </button>
</div>
</div>

## Контекст
- **Заказчик/владелец продукта:** внутренний департамент компании Лилиани
- **Пользователи на технике:** механизатор/оператор/инженер/агроном
- **Пользователи портала:** диспетчер/руководитель/служба эксплуатации/агроном
- **Боль:** контроль и учет собранного урожая; учет намолота и перевезенного урожая для расчета оплаты; снижение/искоренение воровства

## Цель и критерии успеха
- **Точность:** ±1% от веса
- **Диапазон:** до 100 т
- **Условия:** вибрации/удары
- **Частота обновления:** минимум 10 Гц
- **Офлайн:** хранение столько, сколько позволяет память устройства

## Передача данных и портал
- блок → Android: Bluetooth, передача **сырых значений**
- Android → портал: мобильный интернет; отправка по событиям, при отсутствии связи — накопление и отправка пакетами при появлении
- в портал уходили: веса + рейсы/события + гео + время + идентификаторы техники

## Роль и ответственность
Требования, сроки/план, бюджет, подрядчики, координация embedded/android/backend, организация и участие в тестировании, приёмка, риски, внедрение, валидация ПО, обучение, поддержка.

## Этапы
- MVP: 10.2021–02.2022  
- тестирование/валидация/серия: 03.2022–05.2022  
- опытная эксплуатация: 06.2022–11.2022  
- эксплуатация/поддержка/развитие: с 11.2022  

## Команда
- Embedded: 1 (внутренний)
- Android: 1 (подрядчик)
- Backend/портал: 1 (внутренний)
- Frontend/портал: 1 (внутренний)
- QA/тесты/испытания: 3 (внутренние)
- Ты: аналитик, архитектор, PM/PO, техписатель

## Результат
- точность учёта: **+50%**
- прозрачность: **+70%**
- снижение спорных ситуаций: **−80%**
- потери/воровство: **−70%**
- продажи бункеров перегрузчиков: **+20%**

<div class="modal fade" id="case3Artifacts" tabindex="-1" aria-labelledby="case3ArtifactsLabel" aria-hidden="true">
  <div class="modal-dialog modal-lg modal-dialog-centered">
    <div class="modal-content">
      <div class="modal-header">
        <h5 class="modal-title" id="case3ArtifactsLabel">Артефакты (без NDA)</h5>
        <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Закрыть"></button>
      </div>
      <div class="modal-body">
        <ul class="list-group">
          <li class="list-group-item">Скриншоты Android-приложения (обезличенные)</li>
          <li class="list-group-item">Схема архитектуры: блок → Android → портал</li>
          <li class="list-group-item">Пример дашборда/отчёта портала (обезличенный)</li>
          <li class="list-group-item">Чек-лист испытаний/валидации</li>
          <li class="list-group-item">Описание фильтрации/алгоритмов (без исходников)</li>
        </ul>
      </div>
    </div>
  </div>
</div>
