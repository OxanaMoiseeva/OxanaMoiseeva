# ПОРТФОЛИО: ИНЖЕНЕР ПО ТЕСТИРОВАНИЮ

## Обо мне  

Привет! Меня зовут ``Оксана``, я начинающий тестировщик.
В этом репозитории вы можете найти некоторые из моих проектов, выполненных во время обучения и практики.
<br> 

## Навыки и технологии
``Jira``, ``Qase.io``, ``SQL``, ``Postman``, ``Fiddler``, ``Swagger``, ``Trello``, <br>
``SoapUI``, ``Android Studio``, ``xCode``, ``Charles``, ``Git``, ``Chrome DevTools``.

## Проекты

<p> Проект 1: Tест веб-приложения для учителей от Skyeng</p> 

<p>Что нужно было сделать:<p>
<ol> 
<li>Задача Nº1</li> - Тестируем веб-приложение для учителей через интерфейс
<li>Задача Nº2</li> - Тестируем веб-приложение для учителей через API
</ol>

<p>Как я решала:<p> 
  <ol>
    <p>ПЛАН ТЕСТИРОВАНИЯ<p>
      
<li>Объект тестирования:</li>
    
**Продукт:** Личный кабинет учителя

**Функционал:** Личные события

**Заказчик:** *Skyeng*

**Сайт:** [*Skyeng-teachers*](https://new-teachers.skyeng.ru/)<p>

<li>Что покрываем тестами</li>

<p>Основная цель заказчика (user-story)<p>
  
  <p>— Преподаватель может использовать личные события для собственных встреч. Они служат напоминанием, что у преподавателя что-то запланировано на это время.

- Преподаватели могут добавить личные события;
- Удалить личные события;
- Редактировать личные события;<p>

<li>Декомпозиция</li>

<li>Как тестировать</li>

<p>Функциональное/Нефункциональное тестирование:
  
   - Функциональный чек-лист</p>

<p>Тестирование API<p>
								
<p>Регрессионное тестирование:

- Регрессионый чек-лист</p>

<p>Smoke и Приёмочное тестирование:
  
- Тест-кейсы qase.io;
- JSON для импорта в qase.io;
- HTML для оперативного ознакомления</p>

<p>Тестирование требований:
  
- таблица вопросов</p>

<p>Баг-репорты</p>

<p>Результат:</p>

<p>По результатам тестирования считаю, можно выпускать весь продукт на пользователей. Портал готов к релизу, блокирующих багов обнаружено не было, заявленные функции стейкхолдерами работают. Баг, обнаруженный при регресс тестировании с приоритетом HIGH должен быть выполнен, но на данном этапе он не мешает функциональности продукта.</p>

<br>

<p>Тестирую API:<p>

>  <a href="https://api.postman.com/collections/26927821-2f2fb780-3f0c-4880-9875-79707fd94f01?access_key=PMAT-01H84Z8JZ88X93XFG16WG3BQ0Q">Коллекция Постман расписания учителей</a>

<p>Создаю коллекцию в Postman, открываю Chrom Devtools в расписании учителей и вытаскиваю запросы для своей коллекции:<p>

<p>{
	"info": {
		"_postman_id": "9b7d7465-a90d-4373-ba26-9061331feacd",
		"name": "DZ_5OxanaM",
		"schema": "https://schema.getpostman.com/json/collection/v2.1.0/collection.json",
		"_exporter_id": "26927821"
	},
	"item": [
		{
			"name": "Create",
			"item": [
				{
					"name": "Create board",
					"event": [
						{
							"listen": "test",
							"script": {
								"exec": [
									"var key = \"idBoard\"\r",
									"var value = pm.response.json().id\r",
									"\r",
									"pm.collectionVariables.set(key, value)"
								],
								"type": "text/javascript"
							}
						}
					],
					"request": {
						"method": "POST",
						"header": [
							{
								"key": "Cookie",
								"value": "token={{token}}",
								"type": "text"
							}
						],
						"body": {
							"mode": "raw",
							"raw": "{\r\n    \"name\":\"{{$randomCatchPhraseDescriptor}}\",\r\n    \"token\":\"{{token}}\"\r\n}",
							"options": {
								"raw": {
									"language": "json"
								}
							}
						},
						"url": {
							"raw": "{{baseURL}}boards",
							"host": [
								"{{baseURL}}boards"
							]
						}
					},
					"response": []
				},
				{
					"name": "Create list 1",
					"event": [
						{
							"listen": "test",
							"script": {
								"exec": [
									"var key = \"idList\"\r",
									"var value = pm.response.json().id\r",
									"\r",
									"pm.collectionVariables.set(key, value)"
								],
								"type": "text/javascript"
							}
						}
					],
					"request": {
						"method": "POST",
						"header": [
							{
								"key": "Cookie",
								"value": "token={{token}}",
								"type": "text"
							}
						],
						"body": {
							"mode": "raw",
							"raw": "{\r\n    \"name\": \"{{$randomAdjective}}\",\r\n    \"idBoard\": \"{{idBoard}}\",\r\n    \"token\": \"{{token}}\"\r\n}",
							"options": {
								"raw": {
									"language": "json"
								}
							}
						},
						"url": {
							"raw": "{{baseURL}}lists",
							"host": [
								"{{baseURL}}lists"
							]
						}
					},
					"response": []
				},
				{
					"name": "Create list 2",
					"event": [
						{
							"listen": "test",
							"script": {
								"exec": [
									"var key = \"idList2\"\r",
									"var value = pm.response.json().id\r",
									"\r",
									"pm.collectionVariables.set(key, value)"
								],
								"type": "text/javascript"
							}
						}
					],
					"request": {
						"method": "POST",
						"header": [
							{
								"key": "Cookie",
								"value": "token={{token}}",
								"type": "text"
							}
						],
						"body": {
							"mode": "raw",
							"raw": "{\r\n    \"name\": \"{{$randomAbbreviation}}\",\r\n    \"idBoard\": \"{{idBoard}}\",\r\n    \"token\": \"{{token}}\"\r\n}",
							"options": {
								"raw": {
									"language": "json"
								}
							}
						},
						"url": {
							"raw": "{{baseURL}}lists",
							"host": [
								"{{baseURL}}lists"
							]
						}
					},
					"response": []
				},
				{
					"name": "Create card",
					"event": [
						{
							"listen": "test",
							"script": {
								"exec": [
									"var key = \"idCard\"\r",
									"var value = pm.response.json().id\r",
									"\r",
									"pm.collectionVariables.set(key, value)"
								],
								"type": "text/javascript"
							}
						}
					],
					"request": {
						"method": "POST",
						"header": [
							{
								"key": "Cookie",
								"value": "token={{token}}",
								"type": "text"
							}
						],
						"body": {
							"mode": "raw",
							"raw": "{\r\n    \"idList\": \"{{idList}}\",\r\n    \"name\": \"{{$randomCompanyName}}\",\r\n    \"token\": \"{{token}}\"\r\n}",
							"options": {
								"raw": {
									"language": "json"
								}
							}
						},
						"url": {
							"raw": "{{baseURL}}cards",
							"host": [
								"{{baseURL}}cards"
							]
						}
					},
					"response": []
				},
				{
					"name": "Add comment",
					"event": [
						{
							"listen": "test",
							"script": {
								"exec": [
									"var key = \"idComment\"\r",
									"var value = pm.response.json().id\r",
									"\r",
									"pm.collectionVariables.set(key, value)"
								],
								"type": "text/javascript"
							}
						}
					],
					"request": {
						"method": "POST",
						"header": [
							{
								"key": "Cookie",
								"value": "token={{token}}",
								"type": "text"
							}
						],
						"body": {
							"mode": "raw",
							"raw": "{\r\n    \"text\": \"{{$randomCatchPhrase}}\",\r\n    \"token\": \"{{token}}\"\r\n}",
							"options": {
								"raw": {
									"language": "json"
								}
							}
						},
						"url": {
							"raw": "{{baseURL}}cards/{{idCard}}/actions/comments",
							"host": [
								"{{baseURL}}cards"
							],
							"path": [
								"{{idCard}}",
								"actions",
								"comments"
							]
						}
					},
					"response": []
				}
			]
		},
		{
			"name": "View",
			"item": [
				{
					"name": "Get board",
					"event": [
						{
							"listen": "test",
							"script": {
								"exec": [
									"pm.test(\"Status code is 200\", function () {\r",
									"    pm.response.to.have.status(200);\r",
									"});"
								],
								"type": "text/javascript"
							}
						}
					],
					"request": {
						"method": "GET",
						"header": [
							{
								"key": "Cookie",
								"value": "token={{token}}",
								"type": "text"
							}
						],
						"url": {
							"raw": "{{baseURL}}boards/{{idBoard}}",
							"host": [
								"{{baseURL}}boards"
							],
							"path": [
								"{{idBoard}}"
							]
						}
					},
					"response": []
				},
				{
					"name": "Get list",
					"event": [
						{
							"listen": "test",
							"script": {
								"exec": [
									"pm.test(\"Status code is 200\", function () {\r",
									"    pm.response.to.have.status(200);\r",
									"});"
								],
								"type": "text/javascript"
							}
						}
					],
					"request": {
						"method": "GET",
						"header": [
							{
								"key": "Cookie",
								"value": "token={{token}}",
								"type": "text"
							}
						],
						"url": {
							"raw": "{{baseURL}}lists/{{idList}}",
							"host": [
								"{{baseURL}}lists"
							],
							"path": [
								"{{idList}}"
							]
						}
					},
					"response": []
				},
				{
					"name": "Get card",
					"event": [
						{
							"listen": "test",
							"script": {
								"exec": [
									"pm.test(\"Status code is 200\", function () {\r",
									"    pm.response.to.have.status(200);\r",
									"});"
								],
								"type": "text/javascript"
							}
						}
					],
					"request": {
						"method": "GET",
						"header": [
							{
								"key": "Cookie",
								"value": "token={{token}}",
								"type": "text"
							}
						],
						"url": {
							"raw": "{{baseURL}}cards/{{idCard}}",
							"host": [
								"{{baseURL}}cards"
							],
							"path": [
								"{{idCard}}"
							]
						}
					},
					"response": []
				}
			]
		},
		{
			"name": "Update",
			"item": [
				{
					"name": "Update card",
					"request": {
						"method": "PUT",
						"header": [
							{
								"key": "Cookie",
								"value": "token={{token}}",
								"type": "text"
							}
						],
						"body": {
							"mode": "raw",
							"raw": "{\r\n    \"name\": \"Updated name\",\r\n    \"token\": \"{{token}}\"\r\n}",
							"options": {
								"raw": {
									"language": "json"
								}
							}
						},
						"url": {
							"raw": "{{baseURL}}cards/{{idCard}}",
							"host": [
								"{{baseURL}}cards"
							],
							"path": [
								"{{idCard}}"
							]
						}
					},
					"response": []
				},
				{
					"name": "Update card list",
					"request": {
						"method": "PUT",
						"header": [
							{
								"key": "Cookie",
								"value": "token={{token}}",
								"type": "text"
							}
						],
						"body": {
							"mode": "raw",
							"raw": "{\r\n    \"idList\": \"{{idList2}}\",\r\n    \"token\": \"{{token}}\"\r\n}",
							"options": {
								"raw": {
									"language": "json"
								}
							}
						},
						"url": {
							"raw": "{{baseURL}}cards/{{idCard}}",
							"host": [
								"{{baseURL}}cards"
							],
							"path": [
								"{{idCard}}"
							]
						}
					},
					"response": []
				}
			]
		},
		{
			"name": "Delete",
			"item": [
				{
					"name": "Delete card",
					"request": {
						"method": "DELETE",
						"header": [
							{
								"key": "Cookie",
								"value": "token={{token}}",
								"type": "text"
							}
						],
						"body": {
							"mode": "raw",
							"raw": "{\r\n    \"id\": \"{{idCard}}\",\r\n    \"token\": \"{{token}}\"\r\n}",
							"options": {
								"raw": {
									"language": "json"
								}
							}
						},
						"url": {
							"raw": "{{baseURL}}cards/{{idCard}}",
							"host": [
								"{{baseURL}}cards"
							],
							"path": [
								"{{idCard}}"
							]
						}
					},
					"response": []
				},
				{
					"name": "Delete board",
					"request": {
						"method": "DELETE",
						"header": [
							{
								"key": "Cookie",
								"value": "token={{token}}",
								"type": "text"
							}
						],
						"body": {
							"mode": "raw",
							"raw": "{\r\n    \"id\": \"{{idBoard}}\",\r\n    \"token\": \"{{token}}\"\r\n}",
							"options": {
								"raw": {
									"language": "json"
								}
							}
						},
						"url": {
							"raw": "{{baseURL}}boards/{{idBoard}}",
							"host": [
								"{{baseURL}}boards"
							],
							"path": [
								"{{idBoard}}"
							]
						}
					},
					"response": []
				}
			]
		}
	],
	"event": [
		{
			"listen": "prerequest",
			"script": {
				"type": "text/javascript",
				"exec": [
					""
				]
			}
		},
		{
			"listen": "test",
			"script": {
				"type": "text/javascript",
				"exec": [
					""
				]
			}
		}
	],
	"variable": [
		{
			"key": "baseURL",
			"value": "https://trello.com/1/",
			"type": "string"
		},
		{
			"key": "token",
			"value": "",
			"type": "string"
		},
		{
			"key": "idBoard",
			"value": "",
			"type": "string"
		},
		{
			"key": "idList",
			"value": "",
			"type": "string"
		},
		{
			"key": "idList2",
			"value": "",
			"type": "string"
		},
		{
			"key": "idCard",
			"value": "",
			"type": "string"
		},
		{
			"key": "idComment",
			"value": "",
			"type": "string"
		}
	]
}</p>

    
> <ol>
   <li>Получение расписания;</li>  
   <li>Создание события (в будущем, прошлом и настоящем);</li> 
   <li>Редактирование события;</li>  
   <li>Удаление события;</li>
</ol>

>  <a href="https://ma-bug-report.atlassian.net/wiki/spaces/~6286578762e0790069a78743/pages/1310721/.+1+2+.">Ссылка на проект расписания учителей Skyeng<a/>

<p>Выводы (итоги):<p>
  
<ol>
  
Вся моя коллекция прошла успешное тестирование. Платформа работает корректно, что позволяет Пользователю полностью доверять приложению. </p>

</ol>


## Во время обучения тестировали запросы по SOAP

  
<soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
   <soap:Body>
      <CheckTextsResponse xmlns="http://speller.yandex.net/services/spellservice">
         <ArrayOfSpellResult>
            <SpellResult>
               <error code="1" pos="0" row="0" col="0" len="9">
                  <word>здраствуй</word>
                  <s>здравствуй</s>
               </error>
               <error code="1" pos="16" row="0" col="16" len="6">
                  <word>добрае</word>
                  <s>доброе</s>
               </error>
            </SpellResult>
         </ArrayOfSpellResult>
      </CheckTextsResponse>
   </soap:Body>
</soap:Envelope>


<br>


<soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
   <soap:Body>
      <CheckTextsResponse xmlns="http://speller.yandex.net/services/spellservice">
         <ArrayOfSpellResult>
            <SpellResult>
               <error code="1" pos="0" row="0" col="0" len="4">
                  <word>Goot</word>
                  <s>Good</s>
               </error>
               <error code="1" pos="5" row="0" col="5" len="6">
                  <word>mornin</word>
                  <s>morning</s>


## SQL

<p>SELECT s.user_id,
          s.group_id,
          t.group_id,
          t.teacher_id,
          t.email AS teacher_email
FROM group_student AS s
RIGHT OUTER JOIN teacher AS t
ON s.group_id = t.group_id
WHERE s.group_id = 170;</p>

<p>SELECT c.id, c.class AS kat, i.name, i.class FROM animal_classes AS c 
INNER JOIN animal_info AS i ON c.id = i.class
WHERE i.class = 1;</p>



## Контактная информация
- Email: maiceeva2012@gmail.com
- LinkedIn: https://www.linkedin.com/in/oksana-moiseeva/
- https://hh.ru/resume/c1cae50dff0c4757fc0039ed1f52756a4e7a43
- https://t.me/Oxana_33
- Учетные данные можно запросить у меня лично.







