---
title: "Артефакт 6 — Модель данных и БД (таблицы)"
permalink: /artifacts/case_2/artifact_6/
---

<div class="d-flex flex-wrap justify-content-between align-items-center gap-2 mb-3">
  <a class="btn btn-outline-secondary btn-sm" href="{{ '/artifacts/case_2/' | relative_url }}">← К артефактам кейса</a>
  <a class="btn btn-outline-primary btn-sm" href="{{ '/projects/case_2/' | relative_url }}">К кейсу</a>
</div>

# Артефакт 6 — Модель данных и БД

<p class="text-muted mb-3">
Компактное представление модели данных “Дирижёра” для портфолио PM/PO: сущности, связи, источники, владельцы данных и контроли качества.
</p>

<div class="card border shadow-sm mb-4">
  <div class="card-body">
    <div class="row g-3">
      <div class="col-12 col-lg-4">
        <div class="card border h-100">
          <div class="card-body">
            <div class="fw-semibold mb-1">Источник данных</div>
            <div class="text-muted">
              GPS (системы автовождения), телематика (скорость/направление/вес/поломки), ручной ввод (поле/культура/границы/сменное задание).
            </div>
          </div>
        </div>
      </div>
      <div class="col-12 col-lg-4">
        <div class="card border h-100">
          <div class="card-body">
            <div class="fw-semibold mb-1">Зачем модель</div>
            <div class="text-muted">
              Чтобы план, маршруты, карта/Гант и аналитика простоев работали на согласованных идентификаторах и “полных” событиях.
            </div>
          </div>
        </div>
      </div>
      <div class="col-12 col-lg-4">
        <div class="card border h-100">
          <div class="card-body">
            <div class="fw-semibold mb-1">Ключевой принцип</div>
            <div class="text-muted">
              Все события и факты привязываются к: <strong>технике</strong> + <strong>смене</strong> + <strong>полю</strong> + <strong>времени</strong> (+ координаты, если есть).
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</div>

## 1 Сущности (таблица)
<div class="card border shadow-sm mb-4">
  <div class="card-body">
    <div class="table-responsive">
      <table class="table align-middle mb-0">
        <thead>
          <tr>
            <th style="width:80px;">ID</th>
            <th style="min-width:220px;">Сущность</th>
            <th style="min-width:260px;">Назначение</th>
            <th style="min-width:280px;">Ключевые атрибуты (логические)</th>
            <th style="min-width:220px;">Кто создаёт/обновляет</th>
            <th style="min-width:260px;">Кто потребляет</th>
          </tr>
        </thead>
        <tbody>

          <tr>
            <td><span class="badge text-bg-light border">E1</span></td>
            <td class="fw-semibold">Хозяйство / Организация</td>
            <td class="text-muted">Контекст владения данными и прав доступа.</td>
            <td class="text-muted">идентификатор, реквизиты, настройки кампании/сезона</td>
            <td>Админ/руководитель</td>
            <td>Web, отчёты</td>
          </tr>

          <tr>
            <td><span class="badge text-bg-light border">E2</span></td>
            <td class="fw-semibold">Пользователи / Роли</td>
            <td class="text-muted">Разграничение доступа (агроном/диспетчер/исполнитель).</td>
            <td class="text-muted">роль, права, принадлежность к организации</td>
            <td>Админ (Web)</td>
            <td>Web/Mobile</td>
          </tr>

          <tr>
            <td><span class="badge text-bg-light border">E3</span></td>
            <td class="fw-semibold">Поле</td>
            <td class="text-muted">Единица планирования и контроля уборки.</td>
            <td class="text-muted">название/код, площадь, статус, привязка к культуре</td>
            <td>Агроном (ручной ввод)</td>
            <td>Планирование, маршруты, карта</td>
          </tr>

          <tr>
            <td><span class="badge text-bg-light border">E4</span></td>
            <td class="fw-semibold">Границы поля (геометрия)</td>
            <td class="text-muted">Основа маршрутов/полос/контроля выхода за границы.</td>
            <td class="text-muted">геометрия, версия, дата актуализации, автор изменения</td>
            <td>Агроном</td>
            <td>Routing, контроль выполнения</td>
          </tr>

          <tr>
            <td><span class="badge text-bg-light border">E5</span></td>
            <td class="fw-semibold">Культура / Кампания</td>
            <td class="text-muted">Контекст сезонных работ (если используется).</td>
            <td class="text-muted">культура, сезон, параметры кампании</td>
            <td>Агроном</td>
            <td>Планирование, отчёты</td>
          </tr>

          <tr>
            <td><span class="badge text-bg-light border">E6</span></td>
            <td class="fw-semibold">Техника</td>
            <td class="text-muted">Парк: комбайны, БП, зерновозы и др.</td>
            <td class="text-muted">тип, идентификатор, параметры, привязка к телематике/GPS</td>
            <td>Диспетчер/админ</td>
            <td>Планирование, мониторинг, алгоритмы</td>
          </tr>

          <tr>
            <td><span class="badge text-bg-light border">E7</span></td>
            <td class="fw-semibold">Смена</td>
            <td class="text-muted">Интервал работ для контроля плана/факта.</td>
            <td class="text-muted">начало/конец, ответственные, состав техники</td>
            <td>Агроном/диспетчер</td>
            <td>Гант, отчёты</td>
          </tr>

          <tr>
            <td><span class="badge text-bg-light border">E8</span></td>
            <td class="fw-semibold">Сменное задание</td>
            <td class="text-muted">План: что и кем делаем в смену.</td>
            <td class="text-muted">поле, техника, приоритет/очередность, тайминги</td>
            <td>Агроном (ручной ввод)</td>
            <td>Mobile, Гант, контроль выполнения</td>
          </tr>

          <tr>
            <td><span class="badge text-bg-light border">E9</span></td>
            <td class="fw-semibold">Маршрут / План движения</td>
            <td class="text-muted">Инструкция исполнителю: точки/трек/полосы.</td>
            <td class="text-muted">геометрия/точки, порядок, временные окна</td>
            <td>Алгоритм / диспетчер</td>
            <td>Планшет/мобилка, мониторинг</td>
          </tr>

          <tr>
            <td><span class="badge text-bg-light border">E10</span></td>
            <td class="fw-semibold">События / Статусы</td>
            <td class="text-muted">Факт выполнения: движение, работа, простои.</td>
            <td class="text-muted">timestamp, техника, поле/смена, статус, координаты (если есть)</td>
            <td>Телематика / система</td>
            <td>Карта, Гант, аналитика</td>
          </tr>

          <tr>
            <td><span class="badge text-bg-light border">E11</span></td>
            <td class="fw-semibold">Поломки / Инциденты</td>
            <td class="text-muted">Причины простоев и реакция.</td>
            <td class="text-muted">тип/причина, время, техника, комментарий, результат</td>
            <td>Телематика + диспетчер</td>
            <td>Контроль, отчёты</td>
          </tr>

          <tr>
            <td><span class="badge text-bg-light border">E12</span></td>
            <td class="fw-semibold">Погода / Оповещения</td>
            <td class="text-muted">Триггеры для перепланирования.</td>
            <td class="text-muted">параметры прогноза, пороги, время, зона/поле</td>
            <td>Источник погоды + система</td>
            <td>Агроном/диспетчер</td>
          </tr>

        </tbody>
      </table>
    </div>
  </div>
</div>

## 2 Ключевые связи (что к чему привязано)
<div class="card border shadow-sm mb-4">
  <div class="card-body">
    <div class="table-responsive">
      <table class="table align-middle mb-0">
        <thead>
          <tr>
            <th style="width:90px;">Связь</th>
            <th style="min-width:260px;">Источник → Приёмник</th>
            <th style="min-width:300px;">Зачем нужна</th>
            <th style="min-width:260px;">Если связи нет/сломана</th>
            <th style="min-width:260px;">Контроль качества</th>
          </tr>
        </thead>
        <tbody>

          <tr>
            <td><span class="badge text-bg-light border">L1</span></td>
            <td><strong>Поле → Границы</strong></td>
            <td class="text-muted">Маршруты/полосы должны строиться строго в границах поля.</td>
            <td class="text-muted">Маршрут некорректен → рост холостых пробегов.</td>
            <td>Проверки геометрии + версия/история границ.</td>
          </tr>

          <tr>
            <td><span class="badge text-bg-light border">L2</span></td>
            <td><strong>Смена → Сменное задание</strong></td>
            <td class="text-muted">План и ответственность “кто/когда/где работает”.</td>
            <td class="text-muted">Гант и контроль выполнения теряют смысл.</td>
            <td>% заданий, привязанных к смене; число правок после старта.</td>
          </tr>

          <tr>
            <td><span class="badge text-bg-light border">L3</span></td>
            <td><strong>Задание → Маршрут</strong></td>
            <td class="text-muted">Исполнитель получает конкретную траекторию/точки/тайминги.</td>
            <td class="text-muted">Задание “без действий” → игнорируется.</td>
            <td>% заданий с маршрутом; отклонение факт-трек от плана.</td>
          </tr>

          <tr>
            <td><span class="badge text-bg-light border">L4</span></td>
            <td><strong>Техника → Телематика/GPS</strong></td>
            <td class="text-muted">Единая идентификация для статусов, треков и расчётов.</td>
            <td class="text-muted">События “без владельца” → слом аналитики.</td>
            <td>% событий без привязки к технике; лаг поступления данных.</td>
          </tr>

          <tr>
            <td><span class="badge text-bg-light border">L5</span></td>
            <td><strong>События → Смена/Поле</strong></td>
            <td class="text-muted">План vs факт, карта, Гант, разбор простоев.</td>
            <td class="text-muted">Нельзя посчитать KPI по полю/смене.</td>
            <td>% событий без смены/поля; полнота временных рядов.</td>
          </tr>

        </tbody>
      </table>
    </div>
  </div>
</div>

## 3 Контроли качества данных (гейты)
<div class="card border">
  <div class="card-body">
    <ul class="mb-0">
      <li><strong>Геометрия поля:</strong> валидна, не самопересекается, имеет версию и историю изменений.</li>
      <li><strong>GPS:</strong> контроль пропусков/качества, пороги на “плохой сигнал”, метка времени.</li>
      <li><strong>Телематика:</strong> минимальный обязательный набор параметров для расчётов, контроль лагов и пропусков.</li>
      <li><strong>Идентификация:</strong> единые идентификаторы техники и смен/заданий для сцепления плана и факта.</li>
      <li><strong>Ручной ввод:</strong> обязательные поля + проверки и история изменений.</li>
    </ul>
  </div>
</div>
