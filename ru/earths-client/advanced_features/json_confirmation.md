# Как создать JSON подтверждение

Как вы знаете, Earths кошелёк поддерживает расширение возможностей. Так, с помощью Earths кошелька можно отправить [Script транзакцию](/earths-client/advanced_features/script_transaction.md). Эта функция позволяет создать кошелек с возможностью мульти-подписи. Благодаря этому, несколько пользователей могут управлять балансом одного аккаунта. Для упрощения управления подобным аккаунтом мы включили специальный раздел **JSON**.

**Прежде чем начать, пожалуйста, имейте в виду: мы не рекомендуем вам отправлять JSON, если вы неопытный пользователь. Ошибки могут привести к потере средств**.

Итак, чтобы начать использовать все доступные функции приложения, сначала необходимо активировать расширенный функционал.

Кстати, вы можете использовать либо онлайн-версию клиента, либо десктопную версию кошелька для Mac, ПК или Linux. Все версии поддерживают автоматическое обновление! Также вы можете загрузить любую версию Earths кошелька с официального сайта - https://earths.ga/product

Откройте свой Earths кошелек. Затем нажмите кнопку **Настройки** (см. левый нижний угол) ![](/_assets/dark_mode_01.png).

После этого появится окно настроек. В окне настроек установите галочку рядом с пунктом  **Расширенные возможности**.

![](/_assets/advanced_features_01.png)

После этого вы можете закрыть меню настроек. Далее в левом верхнем углу нажмите на кнопку **Отправить**.

![](/_assets/json_01.png)

В появившемся окне выберете необходимую криптовалюту, заполните поля формы и нажмите на кнопку **Продолжить**.

Далее выберете секцию **JSON** и скопируйте код из окна и передайте его тем пользователям, которые должны подписать транзакцию вывода средств из текущего аккаунта.
Вы также можете поделиться с ними **Ссылкой** для осуществления подписи транзакции или позволить им просканировать **QR-код** (раздел **Экспорт**).

![](/_assets/json_03.png)

**Примечание**: Если в Script-транзакции вы указали, что подтвердить вывод средств из аккаунта необходимо трем пользователям, необходимо сообщить полученный код (JSON) всем трём пользователям. При этом они должны подтверждать транзакцию вывода средств в том же порядке, в котором они указаны в Script-транзакции.

После того, как вы передали JSON пользователю для подтверждения вывода средств, ему необходимо нажать на кнопку **<> JSON** в своём аккаунте и ввести его в поле **TX JSON**.

Затем ему нужно нажать на кнопку **Продолжить**.

![](/_assets/json_04.png)

После того как он проверит все данные транзакции, ему останется только дважды нажать кнопку **Подписать** для подтверждения транзакции вывода средств из вашего аккаунта с мульти-подписью.

![](/_assets/json_05.png)

Те же самые действия должны совершить и другие пользователи указанные в Script-транзакции, если их подтверждение необходимо.  

После того, как все пользователи подпишут вашу транзакцию с мульти-аккаунта будет списана указанная вами сумма. Транзакция появится в сети спустя несколько секунд.

___

Если у вас возникнут трудности с использованием нашей платформы, пожалуйста, создайте запрос в [службу поддержки](https://support.earths.ga/) или задайте вопрос на нашем [форуме](https://forum.earths.ga/).
