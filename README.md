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

* [Сбросить расчёт ОСАГО](#osago-stop)

Для начала работы с API необходимо получить секретный ключ для аутентификации, запросив его по адресу info@sc-bit.ru

Ответы имеют формат json.

Базовый URL - https://strahovkaa.ru/api1/


## Создать ОСАГО 
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
			"id":"6829"
		}
	}


### Редактировать ОСАГО

URL – **osago/update**

тип запроса – **POST**

параметры:

	access-token – секретный ключ
	id – ид полиса
	остальные параметры аналогичны запросу создания полиса
	
Пример ответа с ошибкой:

	{
		"name": "Forbidden",
    	"message": "Сначала измените дату начала действия полиса",
    	"code": 0,
    	"status": 403,
    	"type": "yii\\web\\ForbiddenHttpException"
	}

Ответ в случае успеха:

	Аналогичен с созданием полиса


### Рассчитать ОСАГО 

URL – **osago/send**

тип запроса – **GET**

параметры:

	access-token – секретный ключ
	id – ид полиса
	
Пример ответа с ошибкой:

	{
   		"name": "Forbidden",
    	"message": "Сначала измените дату начала действия полиса",
    	"code": 0,
    	"status": 403,
    	"type": "yii\\web\\ForbiddenHttpException"
	}

Ответ в случае успеха:

	{
		"code":0,
		"status":200,
		"message":{
			"message":"OK"
		},
		"data":{
			"id":"6829",
			"status":0,
			"created_at":"2019-07-10 17:47:45",
			"updated_at":"2019-07-10 17:47:45",
			"owner":"613",
			"vehicle_auto_mark_name":"NISSAN",
			"vehicle_auto_mark_id":157,
			"vehicle_auto_model_name":"PATHFINDER",
			"vehicle_auto_model_id":955,
			"vehicle_manufactured_year":"2001",
			"insured_last_name":"ЧЕЧЕЛЬ",
			"insured_first_name":"НИКОЛАЙ",
			"insured_middle_name":"ИВАНОВИЧ",
			"mobile":"9130887400",
			"client_payment_state":0,
			"vehicle_power":86,
			"vehicle_identification_type":"body",
			"vehicle_identification_number":"JN8Y",
			"vehicle_registration_number":"К157ОЕ",
			"vehicle_registration_region":"22",
			"vehicle_document_type":"sertificate",
			"vehicle_document_serie":"4424",
			"vehicle_document_number":"586548",
			"vehicle_document_date":"2018-07-05",
			"vehicle_diagnostic_number":"070420021901679",
			"vehicle_diagnostic_expiry":"2020-04-26",
			"driver_1_last_name":"",
			"driver_1_first_name":"",
			"driver_1_middle_name":"",
			"driver_1_birthday":null,
			"driver_1_license_serie":"",
			"driver_1_license_number":"",
			"driver_1_experience_date":null,
			"insured_birthday":"1990-07-10",
			"insured_passport_serie":"3413",
			"insured_passport_number":"582691",
			"insured_passport_date":"2005-07-10",
			"insured_address_region_name":"Алтайский край ",
			"insured_address_city_name":"Барнаул г ",
			"insured_address_street_name":"Степная 1-я ул",
			"insured_address_home":"1",
			"insured_address_build":"",
			"insured_address_flat":"",
			"last_error":"",
			"email":"test@ya.ru",
			"insured_address_region_code":"2200000000000",
			"insured_address_city_code":"2200000100000",
			"insured_address_street_code":"",
			"owner_last_name":"ЧЕЧЕЛЬ",
			"owner_first_name":"НИКОЛАЙ",
			"owner_middle_name":"ИВАНОВИЧ",
			"owner_birthday":"1990-07-10",
			"owner_passport_serie":"3413",
			"owner_passport_number":"582691",
			"owner_passport_date":"2005-07-10",
			"owner_address_region_name":"Алтайский край ",
			"owner_address_region_code":"2200000000000",
			"owner_address_city_name":"Барнаул г ",
			"owner_address_city_code":"2200000100000",
			"owner_address_street_name":"Степная 1-я ул",
			"owner_address_street_code":"",
			"owner_address_home":"1",
			"owner_address_build":"",
			"owner_address_flat":"",
			"policy_date":"2019-07-14",
			"policy_form_id":0, 
			"alpha_payment_link":"",
			"alpha_policy_number":"",
			"alpha_policy_cost":0, "ingos_model":0,
			"ingos_make":0,
			"ingos_AgrID":"",
			"ingos_ISN":"0",
			"ingos_BillISN":0,
			"ingos_PayURL":"",
			"ingos_status":1,
			"ingos_last_error":"",
			"ingos_PremiumSum":0,
			"sib_make_id":0,
			"sib_model_id":0,
			"paid_date":"0000-00-00 00:00:00",
			"alfa_status":2,
			"alfa_make":"",
			"alfa_model":"",
			"alfa_contractId":"0",
			"alfa_contractNumber":"0",
			"alfa_contractPremium":0,
			"alfa_last_error":"",
			"alfa_formUrl":"",
			"alfa_orderId":"",
			"alfa_upid":"",
			"egarant_id":"",
			"ingos_modification":"",
			"ingos_tb":0,
			"ingos_kt":0,
			"ingos_ks":0,
			"ingos_kvs":0,
			"ingos_kbm":0,
			"ingos_km":0,
			"ingos_kn":0,
			"alfa_tb":0,
			"alfa_kt":0,
			"alfa_kbm":0,
			"alfa_kvs":0,
			"alfa_ks":0,
			"alfa_kp":0,
			"alfa_km":0,
			"alfa_kn":0,
			"alfa_ko":0,
			"alfa_kpr":0,
			"Period_DateBeg_1":"2019-07-14",
			"Period_DateBeg_2":"0000-00-00",
			"period":0,
			"Period_DateEnd_1":"2020-07-13",
			"ingos_ko":0,
			"refer":"0",
			"engine_type":"P",
			"from_app":1,
			"alfa_cross_contractId":"0",
			"vehicle_trailer":0,
			"sib_rgs_payment_link":"",
			"sib_rgs_policy_number":"",
			"sib_rgs_policy_cost":0,
			"sib_rgs_status":0,
			"zetta_status":0,
			"zetta_Premium":0,
			"zetta_ID":"",
			"zetta_last_error":"",
			"zetta_Mark":"",
			"zetta_Model":"",
			"zetta_owl":"0",
			"soglasie_tariff":0,
			"soglasie_ko":0,
			"soglasie_kn":0,
			"soglasie_km":0,
			"soglasie_ks":0,
			"soglasie_kvs":0,
			"soglasie_kbm":0,
			"soglasie_kt":0,
			"soglasie_tb":0,
			"soglasie_last_error":"",
			"soglasie_pass":"",
			"soglasie_sub_status":0,
			"soglasie_request_token":"",
			"soglasie_ID":"0",
			"sib_rgs_last_error":"",
			"sib_rgs_id":"0",
			"sib_rgs_sub_status":0,
			"inomarka":0,
			"zetta_tb":0,
			"zetta_kp":0,
			"zetta_ko":0,
			"zetta_kn":0,
			"zetta_km":0,
			"zetta_ks":0,
			"zetta_kvs":0,
			"zetta_kbm":0,
			"zetta_kt":0,
			"zetta_sub_status":0,
			"zetta_insured_index":"",
			"soglasie_PayLink":"",
			"zetta_QuotationISN":0,
			"zetta_paymentUrl":""
		}
	}
