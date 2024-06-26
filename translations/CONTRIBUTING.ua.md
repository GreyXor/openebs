# Як зробити свій внесок у OpenEBS

Чудово!! Ми завжди у пошуках людей, які можуть покращити OpenEBS. Ви можете почати з [огляду](./contribute/design/README.md)

Перш за все, якщо ви не впевнені в чомусь, або остерігаїтесь, все одно, задайте питання або ж відкрийте issue або ж відправте pull request. Ви не отримаєте шквал критики за прикладені зусилля. Найгірше, що може статись - вас ввічливо попросять щось змінити. Ми цінимо будь-який внесок й не хочемо создавати великий лист правил на шляху до цього.

Тем не менш, ті, хто хоче отримати більш детальні рекомендації про те, як краще зробити свій внесок в проект, читайте далі. Цей документ описує усі місця, які ми перевіряємо у ваших пулл реквестах, й збільшує ваші шанси на швидкий мерж ваших змін.

Тем не менш, OpenEBS - це інновація у Open Source. Ви можете внести свій внесок у будь-який можливий спосіб, та вся допомога, оказана нам, дуже цінується. 

- [Як зробити свій внесок у OpenEBS](#як-зробити-свій-внесок-у-openebs)
  - [Відкриття issue](#відкриття-issue)
  - [Покращення документації](#покращення-документації)
  - [Пропонування нового функціоналу](#пропонування-нового-функціоналу)
  - [Контриб'ют у початковий код й фікс багів](#контрибют-у-початковий-код-й-фікс-багів)
  - [Робота над існуючими задачами](#робота-над-існуючими-задачами)
    - [Підпишить свою роботу!](#підпишить-свою-роботу)
  - [Приєднуйтесь до ком'юніті!](#приєднуйтесь-до-комюніті)

Ось декілька простих пунктів, яким потрібно прямувати перед тим,як відправляти свій код. 

## Відкриття issue

Відкриваючи новий issue, перевірте, що ви вказали:
- Умови перевірки задач мають бути заповнені, як вказано у шаблонах, щоб перевіряючому був яснішим механизм перевірки.
- Сценарій, при якому сталося issue (або зрозумілий спосіб відтворення).
- Помилки та логи, які можуть бути відображені.
- Інші деталі, що можуть бути корисними.

## Покращення документації

Підтримувати документацію завжди важко! Продивиться цю [сторінку](./contribute/CONTRIBUTING-TO-DEVELOPER-DOC.md) для більш подробної інформації як ви можете покращити документацію для розробки, відкривши пулл реквест с потрібним тегом. Ось [лист тегів](./contribute/labels-of-issues.md) які можуть бути використані. Допоможіть нам тримати документацію чистою, легкою й доступною для розуміння.

## Пропонування нового функціоналу

Завжди є ще щось, що потрібно, для задоволення ваших потреб. Не бійтесь приєднатись до обговорень нового функціоналу або зробити pull request з запропонованими змінами. 

- [Приєднуйтесь до нашого товариства](https://kubernetes.slack.com).
  - Вже зареєстровані? Приєднуйтесь до наших обговорень в [#openebs](https://kubernetes.slack.com/messages/openebs/).

## Контриб'ют у початковий код й фікс багів

Створюйте рулл реквести з відповідними тегами для фіксів багів або покращень початкового коду. Лист тегів які можуть бути використані [тут](./contribute/labels-of-issues.md).

* Для контриб'юту у K8s demo, дивиться цей [документ](./contribute/CONTRIBUTING-TO-K8S-DEMO.md).
	- Для інформації як OpenEBS працює з K8s, дивиться цей [документ](https://openebs.io/docs)
-  Для контриб'юту у Kubernetes OpenEBS Provisioner, дивиться цей [документ](./contribute/CONTRIBUTING-TO-KUBERNETES-OPENEBS-PROVISIONER.md).
	
Для інформації о структурі коду й інструкціях, які потрібно виконувати, дивиться [цей документ](./contribute/design/code-structuring.md).

## Робота над існуючими задачами
Продивиться [issues](https://github.com/openebs/openebs/issues) щоб знайти задачі де нужна допомога від учасників. Подивиться нашу [вказівку з міток](./contribute/labels-of-issues.md) яка допоможе вам знайти задачі, які ви зможете вирішити швидше.

Будь хто може внести свій внесок, взявши задачу, попросивши про це у комментарях / назначивши свій Github ID до задачі. Якщо протягом тижня немає пулл реквеста або ж будь яких оновлень щодо прогрессу, задача вважається відкритою знову і її може взяти до роботи хто завгодно. У випадку задач з високим пріорітетом / багів оновлення про статус / прогрес може бути необхідним кожен день або два. 

---
### Підпишить свою роботу!

Ми використовуємо Developer Certificate of Origin (DCO) як додатковий захист для OpenEBS. Це добре розроблений й широковикористовуємий механизм, що дозволяє учасникам підтвердити права на участь у проекті згідно лицензії. Будь ласка, прочитайте [developer-certificate-of-origin](./contribute/developer-certificate-of-origin).

Якщо ви згодні на підпис, лише додайте одну строку к кожному commit message:

````
  Signed-off-by: Random J Developer <random@developer.example.org>
````
або використайте команду `git commit -s -m "commit message comes here"` щоб підписати комміт одразу.

Використовуйте справжні ім'я й прізвище (нажаль, ніяких анонимів або ніків). Якщо ви встановите свої `user.name` та `user.email` у конфигу git'a , ви зможете автоматично підписати коміти з  `git commit -s`. Ви також можете використовувати  [аліаси](https://git-scm.com/book/en/v2/Git-Basics-Git-Aliases) такі як `git config --global alias.ci 'commit -s'`. Тепер ви можете зробити коміт с  `git ci` і він буде підписаним.

---

## Приєднуйтесь до ком'юніті!

Якщо ви хочете активно розвивати й вносити свій внесок у OpenEBS ком'юніті, подивиться цей [документ](./community/README.md).
