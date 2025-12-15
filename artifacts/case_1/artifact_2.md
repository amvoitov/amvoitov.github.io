---
title: "Артефакт 2: NSM и KPI-дерево"
permalink: /artifacts/case_1/artifact_2/
---

<div class="d-flex flex-wrap justify-content-between align-items-start gap-2 mb-3">
  <a class="btn btn-outline-secondary btn-sm" href="{{ '/artifacts/case_1/' | relative_url }}">← К артефактам кейса</a>
  <a class="btn btn-outline-primary btn-sm" href="{{ '/projects/case_1/' | relative_url }}">Открыть кейс</a>
</div>

<div class="card shadow-sm border-0">
  <div class="card-body p-4">
    <h1 class="h3 mb-2">North Star и KPI-дерево</h1>
    <p class="text-secondary mb-0">
      Метрики продукта: North Star Metric и драйверы качества/доставки/безопасности/принятия.
    </p>
  </div>
</div>

<div class="row g-3 mt-1">
  <div class="col-12">
    <div class="card shadow-sm">
      <div class="card-body p-4">
        <div class="d-flex flex-wrap align-items-center gap-2 mb-2">
          <h2 class="h5 mb-0">North Star Metric</h2>
          <span class="badge text-bg-light border">весовая система</span>
        </div>

        <div class="alert alert-light border mb-0">
          <strong>Учтённый подтверждённый вес (тонны)</strong> по операциям БП, доступный владельцу в веб-кабинете за период
          (с корректной идентификацией и чеком).
        </div>
      </div>
    </div>
  </div>

  <div class="col-12">
    <div class="card shadow-sm">
      <div class="card-body p-4">
        <div class="d-flex flex-wrap align-items-center gap-2 mb-3">
          <h2 class="h5 mb-0">Драйверы (KPI-дерево)</h2>
          <span class="badge text-bg-light border">ТЗ Сайт Весовой</span>
          <span class="badge text-bg-light border">ТЗ Web-Automation</span>
        </div>

        <div class="accordion" id="kpiTree">

          <div class="accordion-item">
            <h2 class="accordion-header" id="kpi-quality-h">
              <button class="accordion-button" type="button" data-bs-toggle="collapse" data-bs-target="#kpi-quality" aria-expanded="true" aria-controls="kpi-quality">
                Качество данных операций
              </button>
            </h2>
            <div id="kpi-quality" class="accordion-collapse collapse show" aria-labelledby="kpi-quality-h" data-bs-parent="#kpiTree">
              <div class="accordion-body">
                <ul class="list-group">
                  <li class="list-group-item">
                    <strong>% операций</strong> с типом (загрузка/выгрузка) + временем + GPS + связанной техникой (из БД).
                  </li>
                  <li class="list-group-item">
                    <strong>% операций</strong>, по которым сформирован/сохранён чек (планшет/сайт).
                  </li>
                </ul>
              </div>
            </div>
          </div>

          <div class="accordion-item">
            <h2 class="accordion-header" id="kpi-reliability-h">
              <button class="accordion-button collapsed" type="button" data-bs-toggle="collapse" data-bs-target="#kpi-reliability" aria-expanded="false" aria-controls="kpi-reliability">
                Доставка данных (reliability)
              </button>
            </h2>
            <div id="kpi-reliability" class="accordion-collapse collapse" aria-labelledby="kpi-reliability-h" data-bs-parent="#kpiTree">
              <div class="accordion-body">
                <ul class="list-group">
                  <li class="list-group-item">
                    <strong>% синхронизированных операций</strong> из offline-очереди (планшет хранит до появления сети).
                  </li>
                  <li class="list-group-item">
                    <strong>Ошибки протокола/доставки:</strong> доля “повторов/разрывов” (ack/ретраи).
                  </li>
                </ul>
              </div>
            </div>
          </div>

          <div class="accordion-item">
            <h2 class="accordion-header" id="kpi-security-h">
              <button class="accordion-button collapsed" type="button" data-bs-toggle="collapse" data-bs-target="#kpi-security" aria-expanded="false" aria-controls="kpi-security">
                Безопасность владения данными
              </button>
            </h2>
            <div id="kpi-security" class="accordion-collapse collapse" aria-labelledby="kpi-security-h" data-bs-parent="#kpiTree">
              <div class="accordion-body">
                <ul class="list-group">
                  <li class="list-group-item">
                    <strong>% успешных привязок БП</strong> к хозяйству через имя БВС+код; количество попыток повторной регистрации (контроль истории).
                  </li>
                </ul>
              </div>
            </div>
          </div>

          <div class="accordion-item">
            <h2 class="accordion-header" id="kpi-adoption-h">
              <button class="accordion-button collapsed" type="button" data-bs-toggle="collapse" data-bs-target="#kpi-adoption" aria-expanded="false" aria-controls="kpi-adoption">
                Adoption (принятие пользователями)
              </button>
            </h2>
            <div id="kpi-adoption" class="accordion-collapse collapse" aria-labelledby="kpi-adoption-h" data-bs-parent="#kpiTree">
              <div class="accordion-body">
                <ul class="list-group">
                  <li class="list-group-item">
                    <strong>Активность админа хозяйства:</strong> наличие заполненных справочников (техника/сотрудники).
                  </li>
                  <li class="list-group-item">
                    <strong>Активность сотрудников:</strong> просмотр электронных чеков/календаря в мобильном приложении.
                  </li>
                </ul>
              </div>
            </div>
          </div>

        </div>

        <div class="mt-3 small text-secondary">
          Примечание: формулировки KPI сохранены как в исходном тексте артефакта.
        </div>
      </div>
    </div>
  </div>
</div>
