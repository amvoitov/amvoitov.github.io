---
title: "Артефакт 5 — Top-риски и меры"
permalink: /artifacts/case_2/artifact_5/
---

<div class="d-flex flex-wrap justify-content-between align-items-center gap-2 mb-3">
  <a class="btn btn-outline-secondary btn-sm" href="{{ '/artifacts/case_2/' | relative_url }}">← К артефактам кейса</a>
  <a class="btn btn-outline-primary btn-sm" href="{{ '/projects/case_2/' | relative_url }}">К кейсу</a>
</div>

# Артефакт 5 — Top-риски и меры

<p class="text-muted mb-3">
Короткий реестр “что может пойти не так” + меры и мониторинг. Формат — портфолио PM/PO.  
<small class="text-muted">Примечание: это проектный risk register (модель рисков/мер), без утверждения, что все метрики были подтверждены эксплуатацией.</small>
</p>

<div class="row g-3 mb-4">
  <div class="col-12 col-lg-4">
    <div class="card h-100 border">
      <div class="card-body">
        <div class="fw-semibold mb-1">Фокус</div>
        <div class="text-muted">Планирование, маршруты на поле, контроль выполнения, перепланирование по погоде.</div>
      </div>
    </div>
  </div>
  <div class="col-12 col-lg-4">
    <div class="card h-100 border">
      <div class="card-body">
        <div class="fw-semibold mb-1">Где проявляется</div>
        <div class="text-muted">Web (карта/Гант), планшет/мобильное (задания), интеграции (GPS/телематика), алгоритмы.</div>
      </div>
    </div>
  </div>
  <div class="col-12 col-lg-4">
    <div class="card h-100 border">
      <div class="card-body">
        <div class="fw-semibold mb-1">Как контролируем</div>
        <div class="text-muted">KPI: простои, холостые пробеги, время перепланирования, качество выполнения сменного задания.</div>
      </div>
    </div>
  </div>
</div>

<div class="card border mb-4 shadow-sm">
  <div class="card-body">
    <div class="table-responsive">
      <table class="table align-middle mb-0">
        <thead>
          <tr>
            <th style="width:70px;">ID</th>
            <th>Риск</th>
            <th>Последствие</th>
            <th>Митигирующие меры (что закладывали)</th>
            <th>Мониторинг (как отслеживать)</th>
            <th style="width:220px;">Связанный артефакт</th>
          </tr>
        </thead>
        <tbody>

          <tr>
            <td><span class="badge text-bg-light border">R1</span></td>
            <td>
              <div class="fw-semibold">Некорректные границы поля / геометрия</div>
              <div class="mt-1">
                <span class="badge rounded-pill text-bg-light border me-1">Ручной ввод</span>
                <span class="badge rounded-pill text-bg-light border">Routing</span>
              </div>
            </td>
            <td class="text-muted">
              Неверные маршруты/полосы → “холостые” переезды, срыв таймингов.
            </td>
            <td>
              Валидация геометрии поля (проверки на пересечения/пустоты), версия/история границ,
              подтверждение агрономом “перед стартом”.
            </td>
            <td>
              <div>• % полей с валидной геометрией</div>
              <div>• кол-во правок границ после старта</div>
              <div>• отклонения трека от границ</div>
            </td>
            <td>
              <a href="{{ '/artifacts/case_2/artifact_4/' | relative_url }}" class="badge text-bg-light border text-decoration-none">Dependencies</a>
              <a href="{{ '/artifacts/case_2/artifact_1/' | relative_url }}" class="badge text-bg-light border text-decoration-none">KPI</a>
            </td>
          </tr>

          <tr>
            <td><span class="badge text-bg-light border">R2</span></td>
            <td>
              <div class="fw-semibold">Низкое качество GPS (дрейф/пропуски)</div>
              <div class="mt-1">
                <span class="badge rounded-pill text-bg-light border me-1">GPS</span>
                <span class="badge rounded-pill text-bg-light border">Telemetry</span>
              </div>
            </td>
            <td class="text-muted">
              Ошибки позиции/скорости → неверный контроль выполнения, неверные расчёты маршрутов/таймингов.
            </td>
            <td>
              Фильтрация/сглаживание, пороги качества сигнала, деградация логики при плохом GPS
              (например: режим “контроль по событиям/статусам” вместо точного трека).
            </td>
            <td>
              <div>• % точек с плохим качеством/пропусками</div>
              <div>• время “без GPS” по технике</div>
              <div>• расхождения маршрут ↔ фактический трек</div>
            </td>
            <td>
              <a href="{{ '/artifacts/case_2/artifact_4/' | relative_url }}" class="badge text-bg-light border text-decoration-none">Dependencies</a>
              <a href="{{ '/artifacts/case_2/artifact_1/' | relative_url }}" class="badge text-bg-light border text-decoration-none">KPI</a>
            </td>
          </tr>

          <tr>
            <td><span class="badge text-bg-light border">R3</span></td>
            <td>
              <div class="fw-semibold">Неполные/нестабильные телематические данные</div>
              <div class="mt-1">
                <span class="badge rounded-pill text-bg-light border me-1">Telemetry</span>
                <span class="badge rounded-pill text-bg-light border">Data quality</span>
              </div>
            </td>
            <td class="text-muted">
              Алгоритм оптимизации “видит” картину частично → решения ухудшают логистику/простои.
            </td>
            <td>
              Минимальный обязательный набор параметров для расчётов, контроль пропусков,
              сценарии деградации (работа по укрупнённым правилам при нехватке данных).
            </td>
            <td>
              <div>• % сообщений/событий с отсутствующими полями</div>
              <div>• задержка поступления данных</div>
              <div>• доля техники “без телематики”</div>
            </td>
            <td>
              <a href="{{ '/artifacts/case_2/artifact_1/' | relative_url }}" class="badge text-bg-light border text-decoration-none">KPI</a>
              <a href="{{ '/artifacts/case_2/artifact_3/' | relative_url }}" class="badge text-bg-light border text-decoration-none">Roadmap</a>
            </td>
          </tr>

          <tr>
            <td><span class="badge text-bg-light border">R4</span></td>
            <td>
              <div class="fw-semibold">Ошибки ручного ввода (сменное задание/культура/поле)</div>
              <div class="mt-1">
                <span class="badge rounded-pill text-bg-light border me-1">Manual</span>
                <span class="badge rounded-pill text-bg-light border">Planning</span>
              </div>
            </td>
            <td class="text-muted">
              План “на неверных исходных” → неправильное распределение техники и приоритетов.
            </td>
            <td>
              Справочники/шаблоны, проверки и обязательные поля, разграничение ролей (кто может менять),
              история изменений и быстрый откат.
            </td>
            <td>
              <div>• число исправлений задания после старта</div>
              <div>• количество конфликтов/несоответствий</div>
              <div>• время на корректировку</div>
            </td>
            <td>
              <a href="{{ '/artifacts/case_2/artifact_2/' | relative_url }}" class="badge text-bg-light border text-decoration-none">Story Map</a>
              <a href="{{ '/artifacts/case_2/artifact_6/' | relative_url }}" class="badge text-bg-light border text-decoration-none">Data</a>
            </td>
          </tr>

          <tr>
            <td><span class="badge text-bg-light border">R5</span></td>
            <td>
              <div class="fw-semibold">Погодные изменения → необходимость быстрого переплана</div>
              <div class="mt-1">
                <span class="badge rounded-pill text-bg-light border me-1">Weather</span>
                <span class="badge rounded-pill text-bg-light border">Replanning</span>
              </div>
            </td>
            <td class="text-muted">
              Срыв смены/потери из-за окна погоды → снижение темпа уборки.
            </td>
            <td>
              Уведомления + правила перепланирования (что пересчитываем, какие ограничения),
              SLA на пересчёт и публикацию нового плана.
            </td>
            <td>
              <div>• время перепланирования (target ≤ 15 мин)</div>
              <div>• % смен, где план был перестроен вовремя</div>
              <div>• причины отмен/отката переплана</div>
            </td>
            <td>
              <a href="{{ '/artifacts/case_2/artifact_1/' | relative_url }}" class="badge text-bg-light border text-decoration-none">KPI</a>
              <a href="{{ '/artifacts/case_2/artifact_2/' | relative_url }}" class="badge text-bg-light border text-decoration-none">Story Map</a>
            </td>
          </tr>

          <tr>
            <td><span class="badge text-bg-light border">R6</span></td>
            <td>
              <div class="fw-semibold">Ошибка/дрейф алгоритма оптимизации логистики</div>
              <div class="mt-1">
                <span class="badge rounded-pill text-bg-light border me-1">Algorithms</span>
                <span class="badge rounded-pill text-bg-light border">Logistics</span>
              </div>
            </td>
            <td class="text-muted">
              Решения ухудшают ситуацию: простои растут, комбайны ждут БП/зерновоз.
            </td>
            <td>
              Тест-набор сценариев, симуляции “комбайн ↔ БП ↔ зерновоз”,
              сравнение с “базовым” планом и ручной корректировкой.
            </td>
            <td>
              <div>• простои/холостые пробеги относительно baseline</div>
              <div>• количество ручных корректировок плана</div>
              <div>• инциденты “комбайн остановился из-за логистики”</div>
            </td>
            <td>
              <a href="{{ '/artifacts/case_2/artifact_1/' | relative_url }}" class="badge text-bg-light border text-decoration-none">KPI</a>
              <a href="{{ '/artifacts/case_2/artifact_2/' | relative_url }}" class="badge text-bg-light border text-decoration-none">Story Map</a>
            </td>
          </tr>

          <tr>
            <td><span class="badge text-bg-light border">R7</span></td>
            <td>
              <div class="fw-semibold">Низкое принятие механизаторами/комбайнёрами</div>
              <div class="mt-1">
                <span class="badge rounded-pill text-bg-light border me-1">Adoption</span>
                <span class="badge rounded-pill text-bg-light border">UX</span>
              </div>
            </td>
            <td class="text-muted">
              Задания игнорируются → фактическая уборка расходится с планом.
            </td>
            <td>
              Максимально простой формат: маршрут/точки/полосы + тайминги,
              обучение и “правила работы”, видимость пользы для исполнителя.
            </td>
            <td>
              <div>• качество выполнения сменного задания (target 90%)</div>
              <div>• отклонения от маршрута/таймингов</div>
              <div>• доля техники “вне плана”</div>
            </td>
            <td>
              <a href="{{ '/artifacts/case_2/artifact_1/' | relative_url }}" class="badge text-bg-light border text-decoration-none">KPI</a>
              <a href="{{ '/artifacts/case_2/artifact_2/' | relative_url }}" class="badge text-bg-light border text-decoration-none">Story Map</a>
            </td>
          </tr>

          <tr>
            <td><span class="badge text-bg-light border">R8</span></td>
            <td>
              <div class="fw-semibold">Проблемы интеграций/доступности данных</div>
              <div class="mt-1">
                <span class="badge rounded-pill text-bg-light border me-1">Integrations</span>
                <span class="badge rounded-pill text-bg-light border">Availability</span>
              </div>
            </td>
            <td class="text-muted">
              Данные поступают с задержками или не поступают → контроль и перепланирование “слепые”.
            </td>
            <td>
              Контракт интеграций, ретраи/повторы, кеширование последнего состояния,
              fallback на ручной ввод статусов/событий при сбое.
            </td>
            <td>
              <div>• SLA/доступность интеграций</div>
              <div>• лаг поступления данных</div>
              <div>• доля ручного ввода из-за сбоев</div>
            </td>
            <td>
              <a href="{{ '/artifacts/case_2/artifact_3/' | relative_url }}" class="badge text-bg-light border text-decoration-none">Roadmap</a>
              <a href="{{ '/artifacts/case_2/artifact_4/' | relative_url }}" class="badge text-bg-light border text-decoration-none">Dependencies</a>
            </td>
          </tr>

          <tr>
            <td><span class="badge text-bg-light border">R9</span></td>
            <td>
              <div class="fw-semibold">Производительность Web (карта/Гант) на больших объёмах</div>
              <div class="mt-1">
                <span class="badge rounded-pill text-bg-light border me-1">Web</span>
                <span class="badge rounded-pill text-bg-light border">Scalability</span>
              </div>
            </td>
            <td class="text-muted">
              “Лаги” и медленная реакция → диспетчер не успевает принимать решения.
            </td>
            <td>
              Ограничение детализации на карте по зуму, агрегации/кэш, фоновые расчёты,
              оптимизация отрисовки Ганта.
            </td>
            <td>
              <div>• время загрузки (карта/Гант)</div>
              <div>• время ответа API на ключевых экранах</div>
              <div>• частота “тяжёлых” запросов</div>
            </td>
            <td>
              <a href="{{ '/artifacts/case_2/artifact_3/' | relative_url }}" class="badge text-bg-light border text-decoration-none">Roadmap</a>
              <a href="{{ '/artifacts/case_2/artifact_6/' | relative_url }}" class="badge text-bg-light border text-decoration-none">Data</a>
            </td>
          </tr>

        </tbody>
      </table>
    </div>
  </div>
</div>

<div class="card border">
  <div class="card-body">
    <div class="fw-semibold mb-2">Связь с KPI</div>
    <ul class="mb-0">
      <li><strong>Простои:</strong> target −40%</li>
      <li><strong>Холостые пробеги:</strong> target −30%</li>
      <li><strong>Время уборки поля:</strong> target −20%</li>
      <li><strong>Перепланирование по погоде:</strong> ≤ 15 минут</li>
      <li><strong>Качество выполнения сменного задания:</strong> 90%</li>
    </ul>
  </div>
</div>
