---
title: "Артефакт 6 — Top-риски и меры"
permalink: /artifacts/case_1/artifact_6/
---

# Артефакт 6 — Top-риски и меры

<p class="text-muted mb-3">
Короткий реестр “что может пойти не так” + меры и мониторинг. Формат — портфолио PM/PO (коротко, по делу).
</p>

<div class="row g-3 mb-4">
  <div class="col-12 col-lg-4">
    <div class="card h-100 border">
      <div class="card-body">
        <div class="fw-semibold mb-1">Цель</div>
        <div class="text-muted">Снизить потери данных, спорные ситуации и риски владения данными.</div>
      </div>
    </div>
  </div>
  <div class="col-12 col-lg-4">
    <div class="card h-100 border">
      <div class="card-body">
        <div class="fw-semibold mb-1">Где проявляется</div>
        <div class="text-muted">Android (оффлайн/синхро), Web (привязка/доступ), Hardware (RFID/блокировка), Протокол.</div>
      </div>
    </div>
  </div>
  <div class="col-12 col-lg-4">
    <div class="card h-100 border">
      <div class="card-body">
        <div class="fw-semibold mb-1">Как контролируем</div>
        <div class="text-muted">KPI: % синхронизации offline-очереди, ошибки доставки (ack/ретраи), попытки повторной регистрации, качество данных операций.</div>
      </div>
    </div>
  </div>
</div>

<div class="card border mb-4">
  <div class="card-body">
    <div class="table-responsive">
      <table class="table align-middle mb-0">
        <thead>
          <tr>
            <th style="width:70px;">ID</th>
            <th>Риск</th>
            <th>Последствие</th>
            <th>Митигирующие меры (что сделали)</th>
            <th>Мониторинг (как отслеживали)</th>
            <th style="width:190px;">Связанный артефакт/ТЗ</th>
          </tr>
        </thead>
        <tbody>

          <tr>
            <td><span class="badge text-bg-light border">R1</span></td>
            <td>
              <div class="fw-semibold">Нет сети в поле</div>
              <div class="mt-1">
                <span class="badge rounded-pill text-bg-light border me-1">Android</span>
                <span class="badge rounded-pill text-bg-light border me-1">Offline</span>
                <span class="badge rounded-pill text-bg-light border">Delivery</span>
              </div>
            </td>
            <td class="text-muted">
              Потери данных / падение доверия к системе учёта.
            </td>
            <td>
              Offline-накопление: очередь операций на устройстве + отправка пакетами при появлении сети.
              <div class="text-muted small mt-1">Данные хранятся столько, сколько позволяет память устройства.</div>
            </td>
            <td>
              <div>• <span class="fw-semibold">% синхронизированных операций из offline-очереди</span></div>
              <div>• “хвост” очереди (сколько несинхронизировано)</div>
            </td>
            <td>
              <span class="badge text-bg-light border">ТЗ “Сайт Сесовой”</span>
            </td>
          </tr>

          <tr>
            <td><span class="badge text-bg-light border">R2</span></td>
            <td>
              <div class="fw-semibold">Ошибка привязки / владения данными</div>
              <div class="mt-1">
                <span class="badge rounded-pill text-bg-light border me-1">Web</span>
                <span class="badge rounded-pill text-bg-light border">Security</span>
              </div>
            </td>
            <td class="text-muted">
              Чужая привязка, спорные ситуации по “чьё устройство/данные”.
            </td>
            <td>
              Привязка БП через <span class="fw-semibold">имя БВС + код</span> + <span class="fw-semibold">история регистраций</span> (контроль повторных/чужих привязок).
            </td>
            <td>
              <div>• <span class="fw-semibold">% успешных привязок</span> (имя БВС + код)</div>
              <div>• <span class="fw-semibold">кол-во попыток повторной регистрации</span></div>
            </td>
            <td>
              <span class="badge text-bg-light border">ТЗ Web-Automation</span>
            </td>
          </tr>

          <tr>
            <td><span class="badge text-bg-light border">R3</span></td>
            <td>
              <div class="fw-semibold">RFID “читает не то” (рядом много меток)</div>
              <div class="mt-1">
                <span class="badge rounded-pill text-bg-light border me-1">Hardware</span>
                <span class="badge rounded-pill text-bg-light border me-1">RFID</span>
                <span class="badge rounded-pill text-bg-light border">Rules</span>
              </div>
            </td>
            <td class="text-muted">
              Неверная идентификация техники → неверные операции/чеки.
            </td>
            <td>
              Правило <span class="fw-semibold">“ближайшее ТС”</span> + <span class="fw-semibold">ручное разрешение</span> (fallback на ручной выбор).
            </td>
            <td>
              <div>• доля операций с ручным подтверждением</div>
              <div>• жалобы/инциденты “не та техника”</div>
            </td>
            <td>
              <span class="badge text-bg-light border">“Свой-Чужой”</span>
            </td>
          </tr>

          <tr>
            <td><span class="badge text-bg-light border">R4</span></td>
            <td>
              <div class="fw-semibold">Отказ блокировки шнека</div>
              <div class="mt-1">
                <span class="badge rounded-pill text-bg-light border me-1">Hardware</span>
                <span class="badge rounded-pill text-bg-light border">Safety</span>
              </div>
            </td>
            <td class="text-muted">
              Не срабатывает сценарий ограничения → риск потерь/воровства.
            </td>
            <td>
              <span class="fw-semibold">Аварийное отключение</span> + <span class="fw-semibold">логирование отказов</span> (фиксировать, когда/почему не сработало).
            </td>
            <td>
              <div>• события “отказ/аварийное отключение”</div>
              <div>• статистика отказов по периодам</div>
            </td>
            <td>
              <span class="badge text-bg-light border">“Свой-Чужой”</span>
            </td>
          </tr>

          <tr>
            <td><span class="badge text-bg-light border">R5</span></td>
            <td>
              <div class="fw-semibold">Надёжность протокола (ack/ретраи/переподключение)</div>
              <div class="mt-1">
                <span class="badge rounded-pill text-bg-light border me-1">Protocol</span>
                <span class="badge rounded-pill text-bg-light border">Reliability</span>
              </div>
            </td>
            <td class="text-muted">
              Дубли/разрывы, “плавающие” данные, потеря доверия к показаниям.
            </td>
            <td>
              Ack + ретраи + переподключение + защита от дублей на приёме (идемпотентность по событиям).
            </td>
            <td>
              <div>• <span class="fw-semibold">ошибки протокола/доставки</span>: доля повторов/разрывов</div>
              <div>• распределение ретраев по периодам</div>
            </td>
            <td>
              <span class="badge text-bg-light border">Весовая система</span>
            </td>
          </tr>

          <tr>
            <td><span class="badge text-bg-light border">R6</span></td>
            <td>
              <div class="fw-semibold">Низкое принятие сотрудниками</div>
              <div class="mt-1">
                <span class="badge rounded-pill text-bg-light border me-1">Adoption</span>
                <span class="badge rounded-pill text-bg-light border">Employee App</span>
              </div>
            </td>
            <td class="text-muted">
              Данные есть “в системе”, но не используются → эффекта нет.
            </td>
            <td>
              Упрощённый сценарий: <span class="fw-semibold">календарь + электронные чеки</span>, минимум действий для пользователя.
            </td>
            <td>
              <div>• просмотры электронных чеков/календаря</div>
              <div>• активность админа (заполненность справочников)</div>
            </td>
            <td>
              <span class="badge text-bg-light border">ТЗ Web-Automation</span>
            </td>
          </tr>

        </tbody>
      </table>
    </div>
  </div>
</div>

<div class="card border">
  <div class="card-body">
    <div class="fw-semibold mb-2">Связь с KPI-деревом</div>
    <ul class="mb-0">
      <li><strong>Delivery:</strong> % синхронизированных операций из offline-очереди, ошибки протокола (ack/ретраи).</li>
      <li><strong>Data quality:</strong> % операций с типом + временем + GPS + связанной техникой; наличие чеков.</li>
      <li><strong>Security:</strong> успешные привязки БП (имя БВС + код), попытки повторной регистрации.</li>
      <li><strong>Adoption:</strong> активность админа (справочники), просмотры чеков/календаря.</li>
    </ul>
  </div>
</div>
