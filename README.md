# Strahovkaa.ru

**strahovkaa.ru**  - это удобная платформа для страховых агентов, брокеров и частных лиц, которая позволяет:

— оформлять любые виды страхования на одном сайте;
	
— получать вознаграждение за все проданные полисы;

— создавать собственную сеть агентов и увеличивать свой доход.

Для оформления полиса необходимы данные следующих документов:

	● Водительское удостоверение (ВУ);

	● Паспорт собственника, страхователя;

	● Паспорт транспортного средства (ПТС) или свидетельство о регистрации транспортного средства (СТС);

	● Диагностическая карта (только для автомобилей старше 3 лет).

# Описание API по оформлению полисов ОСАГО:

## Содержание:

* [Создать ОСАГО](#osago-create)

* [Редактировать ОСАГО](#osago-update)

* [Рассчитать ОСАГО](#osago-send)

* [Создать ОСАГО](#osago-create)

* [Сбросить расчёт ОСАГО](#osago-stop)

Для начала работы с API необходимо получить секретный ключ для аутентификации, запросив его по адресу info@sc-bit.ru

Ответы имеют формат json.

Базовый URL - https://strahovkaa.ru/api1/


### Создать ОСАГО
URL – **osago/create**

тип запроса – **POST**

параметры:

	access-token – секретный ключ
	vehicle_auto_mark_name – марка авто
	vehicle_auto_mark_id – ид марки авто
	vehicle_auto_model_name – модель авто
	vehicle_auto_model_id – ид модели авто
	vehicle_manufactured_year – год выпуска авто
	vehicle_power – мощность авто, л.с.
	vehicle_identification_type – тип идентификатора ТС (может принимать значения: body – номер кузова,
	vin – вин код, chassis – номер шасси)
	vehicle_identification_number – идентификационный номер
	vehicle_registration_number – регистрационный номер (без региона)
	vehicle_registration_region – регион регистрационного номера
	vehicle_document_type – тип документа (может принимать значения: sertificate  - СТС, passport – ПТС)
	vehicle_document_serie – серия документа
	vehicle_document_number – номер документа
	vehicle_document_date – дата выдачи документа
	vehicle_diagnostic_number – номер диагностической карты
	vehicle_diagnostic_expiry – дата окончания действия диагностической карты
	insured_last_name – фамилия страхователя
	insured_first_name – имя страхователя
	insured_middle_name – отчество страхователя
	insured_birthday – дата рождения страхователя
	insured_passport_serie – серия паспорта страхователя
	insured_passport_number – номер паспорта страхователя
	insured_passport_date – дата выдачи паспорта страхователя
	insured_address_region_name – регион страхователя
	insured_address_region_code – код региона страхователя
	insured_address_city_name – город страхователя
	insured_address_city_code – код города страхователя
	insured_address_street_name – улица страхователя
	insured_address_street_code – код улицы страхователя
	insured_address_home – номер дома страхователя
	insured_address_build – корпус страхователя
	insured_address_flat – квартира страхователя
	owner_last_name – фамилия собственника
	owner_first_name – имя собственника
	owner_middle_name – отчество собственника
	owner_birthday – дата рождения собственника
	owner_passport_serie – серия паспорта собственника
	owner_passport_number – номер паспорта собственника
	owner_passport_date – дата выдачи паспорта собственника
	owner_address_region_name – регион собственника
	owner_address_region_code – код региона собственника
	owner_address_city_name – город собственника
	owner_address_city_code – код города собственника
	owner_address_street_name – улица собственника
	owner_address_street_code – код улицы собственника
	owner_address_home – номер дома собственника
	owner_address_build – корпус собственника
	owner_address_flat – квартира собственника
	driver_1_last_name – фамилия 1го водителя
	driver_1_first_name – имя 1го водителя
	driver_1_middle_name – отчество 1го водителя
	driver_1_birthday – дата рождения 1го водителя
	driver_1_license_serie – серия вод. удостоверения
	driver_1_license_number – номер вод. удостоверения
	driver_1_experience_date – дата выдачи первого удостоверения
	policy_date – дата начала действия полиса (не менее 3х дней с текущей даты)
	адрес электронной почты и номер мобильного телефона должны быть обязательно уникальные для каждого клиента,
	чтобы потом можно было получить доступ в личный кабинет страховой компании,
	на адрес электронной почты страховая компания направит полис ОСАГО
	email – электронная почта
	mobile – номер мобильного телефона
		
Ответ в случае успеха:

	{
	"code":0,
	"status":200,
	"message":{
	"message":"OK"
	},
	"data":{
	"driver_1_experience_date":"",
	"vehicle_identification_number":"JN8Y",
	"vehicle_auto_mark_name":"NISSAN",
	"insured_address_home":"1",
	"insured_address_flat":"",
	"insured_last_name":"ЧЕЧЕЛЬ",
	"insured_address_region_code":"2200000000000",
	"insured_first_name":"НИКОЛАЙ",
	"vehicle_registration_region":"22",
	"vehicle_document_serie":"4424",
	"owner_passport_date":"2005-07-10",
	"vehicle_document_number":"586548",
	"owner_address_street_name":"Степная 1-я ул",
	"driver_1_middle_name":"",
	"insured_address_street_code":"",
	"owner_passport_number":"582691",
	"owner_address_city_name":"Барнаул г ",
	"insured_address_build":"",
	"mobile":"85642145",
	"vehicle_identification_type":"body",
	"email":"test@ya.ru",
	"driver_1_license_number":"",
	"driver_1_first_name":"",
	"owner_middle_name":"ИВАНОВИЧ",
	"insured_passport_date":"2005-07-10",
	"owner_address_home":"1",
	"insured_address_city_name":"Барнаул г ",
	"insured_passport_number":"582691",
	"vehicle_diagnostic_expiry":"2020-04-26",
	"vehicle_auto_mark_id":"157",
	"vehicle_auto_model_name":"PATHFINDER",
	"owner_passport_serie":"3413",
	"owner_birthday":"1990-07-10",
	"owner_address_street_code":"",
	"vehicle_document_date":"2018-07-05",
	"insured_address_street_name":"Степная 1-я ул",
	"insured_address_city_code":"2200000100000",
	"owner_address_city_code":"2200000100000",
	"vehicle_diagnostic_number":"070420021901679",
	"owner_address_region_name":"Алтайский край ",
	"driver_1_last_name":"",
	"insured_passport_serie":"3413",
	"vehicle_manufactured_year":"2001",
	"vehicle_auto_model_id":"955",
	"owner_first_name":"НИКОЛАЙ",
	"owner_address_region_code":"2200000000000",
	"driver_1_license_serie":"",
	"from_app":"1",
	"insured_middle_name":"ИВАНОВИЧ",
	"owner_address_build":"",
	"owner_last_name":"ЧЕЧЕЛЬ",
	"policy_date":"2019-07-14",
	"insured_address_region_name":"Алтайский край ",
	"vehicle_power":"86",
	"driver_1_birthday":"",
	"owner_address_flat":"",
	"vehicle_document_type":"sertificate",
	"vehicle_registration_number":"К157ОЕ",
	"insured_birthday":"1990-07-10",
	"Period_DateBeg_1":"2019-07-14",
	"Period_DateEnd_1":"2020-07-13",
	"owner":"613",
	"created_at":"2019-07-10 17:47:45",
	"updated_at":"2019-07-10 17:47:45",
	"id":"6829"}}


### Редактировать ОСАГО

