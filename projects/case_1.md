---
title: "Кейс 1: Весовая ЛИЛИАНИ"
permalink: /projects/case_1/
---

<div class="d-flex justify-content-between align-items-center mb-3">
  <a class="btn btn-outline-secondary btn-sm" href="{{ '/projects/' | relative_url }}">← Назад к проектам</a>
</div>

# Весовая система для бункера-перегрузчика

<div class="row g-3 mb-3">
  <div class="col-12 col-lg-8">
    <div class="card shadow-sm">
      <div class="card-body">
        <p class="lead mb-2">
          Система взвешивания для бункера-перегрузчика: блок обработки сигнала тензодатчиков + Android-приложение (отображение, логика, фильтрация)
          + портал аналитики/телеметрии.
        </p>

        <div class="d-flex flex-wrap gap-2 mb-3">
          <span class="badge text-bg-light border">Embedded</span>
          <span class="badge text-bg-light border">Android</span>
          <span class="badge text-bg-light border">Портал аналитики</span>
          <span class="badge text-bg-light border">Телеметрия</span>
          <span class="badge text-bg-light border">Интеграции</span>
          <span class="badge text-bg-light border">Качество данных</span>
        </div>

        <div class="alert alert-light border mb-0">
          <b>Цель:</b> контроль и учёт собранного/перевезённого урожая, расчёт оплаты механизаторов/водителей, снижение потерь/воровства.
        </div>
      </div>
    </div>
  </div>

  <div class="col-12 col-lg-4">
    <div class="card shadow-sm h-100">
      <div class="card-body">
        <div class="fw-semibold mb-2">Роль</div>
        <div class="d-flex flex-wrap gap-2 mb-3">
          <span class="badge text-bg-primary">PM</span>
          <span class="badge text-bg-primary">PO</span>
          <span class="badge text-bg-primary">Аналитик</span>
          <span class="badge text-bg-primary">Техлид</span>
          <span class="badge text-bg-primary">Архитектор</span>
          <span class="badge text-bg-primary">Техписатель</span>
        </div>

        <div class="fw-semibold mb-2">Заказчик / владелец продукта</div>
        <div class="mb-3">Внутренний департамент компании «Лилиани»</div>

        <div class="fw-semibold mb-2">Пользователи</div>
        <ul class="mb-0">
          <li>На технике: механизатор/оператор/инженер/агроном</li>
          <li>Портал: диспетчер/руководитель/служба эксплуатации/агроном</li>
        </ul>
      </div>
    </div>
  </div>
</div>

---

## Контекст

<div class="card shadow-sm mb-3">
  <div class="card-body">
    <div class="row g-3">
      <div class="col-12 col-lg-6">
        <div class="fw-semibold mb-2">Исходная боль</div>
        <ol class="mb-0">
          <li>Контроль и учёт собранного урожая</li>
          <li>Учёт намолота и перевезённого урожая для расчёта оплаты</li>
          <li>Снижение / искоренение воровства урожая</li>
        </ol>
      </div>

      <div class="col-12 col-lg-6">
        <div class="fw-semibold mb-2">Ограничения и требования (ключевые)</div>
        <ul class="mb-0">
          <li>Точность: <b>±1%</b> от взвешиваемого веса</li>
          <li>Диапазон массы: до <b>100 тонн</b></li>
          <li>Условия эксплуатации: вибрации / удары</li>
          <li>Обновление на экране: минимум <b>10 Гц</b></li>
        </ul>
      </div>
    </div>
  </div>
</div>

---

## Цель и критерии успеха

<div class="card shadow-sm mb-3">
  <div class="card-body">
    <div class="fw-semibold mb-2">Критерии (в терминах проверяемых требований)</div>

    <div class="table-responsive">
      <table class="table table-sm align-middle">
        <thead>
          <tr>
            <th style="width: 42%;">Параметр</th>
            <th>Требование</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td>Погрешность измерения</td>
            <td>±1% от взвешиваемого веса</td>
          </tr>
          <tr>
            <td>Диапазон массы</td>
            <td>до 100 т</td>
          </tr>
          <tr>
            <td>Частота обновления UI</td>
            <td>не ниже 10 Гц</td>
          </tr>
          <tr>
            <td>Эксплуатация</td>
            <td>устойчивость к вибрациям и ударам</td>
          </tr>
          <tr>
            <td>Связь</td>
            <td>Bluetooth, передача “сырых значений”</td>
          </tr>
          <tr>
            <td>Оффлайн-режим</td>
            <td>Android хранит данные в памяти устройства до появления связи</td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</div>

---

## Решение и потоки данных

<div class="row g-3 mb-3">
  <div class="col-12 col-lg-6">
    <div class="card shadow-sm h-100">
      <div class="card-body">
        <div class="fw-semibold mb-2">Контур “техника → Android”</div>
        <ul class="mb-0">
          <li>Канал: Bluetooth</li>
          <li>Что передавали: “сырые значения”</li>
          <li>На Android: логика отображения и фильтрации данных</li>
          <li>Оффлайн: да — хранение по объёму памяти устройства</li>
        </ul>
      </div>
    </div>
  </div>

  <div class="col-12 col-lg-6">
    <div class="card shadow-sm h-100">
      <div class="card-body">
        <div class="fw-semibold mb-2">Контур “Android → портал”</div>
        <ul class="mb-0">
          <li>Кто отправляет: Android-приложение</li>
          <li>Канал в интернет: мобильный интернет</li>
          <li>Отправка: по событию при наличии соединения; пакетами при восстановлении</li>
          <li>Что уходило: веса + рейсы/события + гео + время + идентификаторы техники</li>
        </ul>
      </div>
    </div>
  </div>
</div>

---

## Моя роль и зона ответственности

<div class="card shadow-sm mb-3">
  <div class="card-body">
    <ul class="mb-0">
      <li>Требования</li>
      <li>План/сроки</li>
      <li>Бюджет</li>
      <li>Подрядчики</li>
      <li>Координация Embedded / Android / Backend</li>
      <li>Организация и участие в тестировании</li>
      <li>Приёмка</li>
      <li>Риски</li>
      <li>Внедрение</li>
      <li>Валидация ПО</li>
      <li>Обучение</li>
      <li>Поддержка и развитие функционала</li>
    </ul>
  </div>
</div>

---

## Команда

<div class="card shadow-sm mb-3">
  <div class="card-body">
    <div class="table-responsive">
      <table class="table table-sm align-middle mb-0">
        <thead>
          <tr>
            <th>Направление</th>
            <th style="width: 25%;">Состав</th>
            <th>Формат</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td>Embedded (блок)</td>
            <td>1</td>
            <td>внутренний сотрудник</td>
          </tr>
          <tr>
            <td>Android</td>
            <td>1</td>
            <td>подрядчик</td>
          </tr>
          <tr>
            <td>Backend/портал</td>
            <td>1</td>
            <td>внутренний сотрудник</td>
          </tr>
          <tr>
            <td>Frontend/портал</td>
            <td>1</td>
            <td>внутренний сотрудник</td>
          </tr>
          <tr>
            <td>QA/тесты/испытания</td>
            <td>3</td>
            <td>внутренние сотрудники</td>
          </tr>
          <tr>
            <td><b>Я</b></td>
            <td>1</td>
            <td>PM/PO/аналитик/архитектор/техписатель</td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</div>

---

## Этапы (таймлайн)

<div class="card shadow-sm mb-3">
  <div class="card-body">
    <div class="list-group">
      <div class="list-group-item">
        <div class="fw-semibold">MVP</div>
        <div class="text-muted">октябрь 2021 — февраль 2022</div>
      </div>
      <div class="list-group-item">
        <div class="fw-semibold">Тестирования / испытания / валидация / внедрение в серийное производство</div>
        <div class="text-muted">март 2022 — май 2022</div>
      </div>
      <div class="list-group-item">
        <div class="fw-semibold">Опытная эксплуатация</div>
        <div class="text-muted">июнь 2022 — ноябрь 2022</div>
      </div>
      <div class="list-group-item">
        <div class="fw-semibold">Эксплуатация и поддержка, доработка функционала</div>
        <div class="text-muted">с ноября 2022</div>
      </div>
    </div>
  </div>
</div>

---

## Результаты

<div class="row g-3 mb-4">
  <div class="col-12 col-md-6 col-xl-4">
    <div class="card shadow-sm h-100">
      <div class="card-body">
        <div class="fw-semibold">Точность учёта</div>
        <div class="display-6">+50%</div>
      </div>
    </div>
  </div>

  <div class="col-12 col-md-6 col-xl-4">
    <div class="card shadow-sm h-100">
      <div class="card-body">
        <div class="fw-semibold">Прозрачность</div>
        <div class="display-6">+70%</div>
      </div>
    </div>
  </div>

  <div class="col-12 col-md-6 col-xl-4">
    <div class="card shadow-sm h-100">
      <div class="card-body">
        <div class="fw-semibold">Снижение спорных ситуаций</div>
        <div class="display-6">−80%</div>
      </div>
    </div>
  </div>

  <div class="col-12 col-md-6 col-xl-6">
    <div class="card shadow-sm h-100">
      <div class="card-body">
        <div class="fw-semibold">Потери / воровство</div>
        <div class="display-6">−70%</div>
      </div>
    </div>
  </div>

  <div class="col-12 col-md-6 col-xl-6">
    <div class="card shadow-sm h-100">
      <div class="card-body">
        <div class="fw-semibold">Продажи бункеров-перегрузчиков</div>
        <div class="display-6">+20%</div>
      </div>
    </div>
  </div>
</div>
