{
  "info": {
    "_postman_id": "5621e7f8-2b93-4f63-be3b-a051bbff33d6",
    "name": "Тренажер пицца",
    "schema": "https://schema.getpostman.com/json/collection/v2.1.0/collection.json",
    "_exporter_id": "51898750",
    "_collection_link": "https://go.postman.co/collection/51898750-5621e7f8-2b93-4f63-be3b-a051bbff33d6?source=collection_link"
  },
  "item": [
    {
      "name": "Регистарция/авторизация",
      "item": [
        {
          "name": "Регистрация пользователя",
          "request": {
            "method": "POST",
            "header": [],
            "body": {
              "mode": "raw",
              "raw": "{\n    \"email\": \"protsenkosava@mail.ru\",\n    \"password\": \"05111998\",\n    \"token\": \"bYCE4E9feT1NMP51K61wBT7CjZ0GykCU50c8UsgYhr\"\n}",
              "options": {
                "raw": {
                  "language": "json"
                }
              }
            },
            "url": {
              "raw": "{{pizzaURL}}/authenticate/register",
              "host": [
                "{{pizzaURL}}"
              ],
              "path": [
                "authenticate",
                "register"
              ]
            }
          },
          "response": []
        },
        {
          "name": "Авторизация",
          "request": {
            "method": "POST",
            "header": [],
            "body": {
              "mode": "raw",
              "raw": "{\n    \"email\": \"protsenkosava@mail.ru\",\n    \"password\": \"05111998\"\n}",
              "options": {
                "raw": {
                  "language": "json"
                }
              }
            },
            "url": {
              "raw": "{{pizzaURL}}/authenticate",
              "host": [
                "{{pizzaURL}}"
              ],
              "path": [
                "authenticate"
              ]
            }
          },
          "response": []
        },
        {
          "name": "Повышение до admin",
          "request": {
            "method": "POST",
            "header": [],
            "body": {
              "mode": "raw",
              "raw": "{\n    \"email\": \"protsenkosava@mail.ru\",\n    \"password\": \"05111998\",\n    \"token\": \"bYCE4E9feT1NMP51K61wBT7CjZ0GykCU50c8UsgYhr\",\n    \"role\": \"admin\"\n}"
            },
            "url": {
              "raw": "{{pizzaURL}}/authenticate/upgrade",
              "host": [
                "{{pizzaURL}}"
              ],
              "path": [
                "authenticate",
                "upgrade"
              ]
            }
          },
          "response": []
        }
      ]
    },
    {
      "name": "Запросы под user",
      "item": [
        {
          "name": "заказы",
          "item": [
            {
              "name": "Cоздать заказ",
              "request": {
                "method": "POST",
                "header": [],
                "body": {
                  "mode": "raw",
                  "raw": "{\n    \"items\": [\n        {\n            \"pizza_id\": \"a644cc31-7f2a-4783-b01c-05224ed4a160\",\n            \"pizzasize_id\": \"7414e8f1-981a-40ae-9ce1-e036d74efb81\",\n            \"quantity\": 1\n        }\n    ]\n}",
                  "options": {
                    "raw": {
                      "language": "json"
                    }
                  }
                },
                "url": {
                  "raw": "{{pizzaURL}}/api/orders",
                  "host": [
                    "{{pizzaURL}}"
                  ],
                  "path": [
                    "api",
                    "orders"
                  ]
                }
              },
              "response": []
            },
            {
              "name": "Инфо о заказе",
              "protocolProfileBehavior": {
                "disableBodyPruning": true
              },
              "request": {
                "method": "GET",
                "header": [],
                "body": {
                  "mode": "raw",
                  "raw": ""
                },
                "url": {
                  "raw": "{{pizzaURL}}/api/orders/b6462cd0-37aa-4e3f-a4d6-78dcc94a9685",
                  "host": [
                    "{{pizzaURL}}"
                  ],
                  "path": [
                    "api",
                    "orders",
                    "b6462cd0-37aa-4e3f-a4d6-78dcc94a9685"
                  ]
                }
              },
              "response": []
            },
            {
              "name": "Инфо о всех заказах пользователя",
              "protocolProfileBehavior": {
                "disableBodyPruning": true
              },
              "request": {
                "method": "GET",
                "header": [],
                "body": {
                  "mode": "raw",
                  "raw": ""
                },
                "url": {
                  "raw": "{{pizzaURL}}/api/orders",
                  "host": [
                    "{{pizzaURL}}"
                  ],
                  "path": [
                    "api",
                    "orders"
                  ],
                  "query": [
                    {
                      "key": "currentPage",
                      "value": "1",
                      "disabled": true
                    },
                    {
                      "key": "_rsc",
                      "value": "1mmep",
                      "disabled": true
                    }
                  ]
                }
              },
              "response": []
            },
            {
              "name": "Оплата заказа",
              "request": {
                "method": "POST",
                "header": [],
                "body": {
                  "mode": "raw",
                  "raw": "",
                  "options": {
                    "raw": {
                      "language": "json"
                    }
                  }
                },
                "url": {
                  "raw": "{{pizzaURL}}/api/orders/b6462cd0-37aa-4e3f-a4d6-78dcc94a9685/pay",
                  "host": [
                    "{{pizzaURL}}"
                  ],
                  "path": [
                    "api",
                    "orders",
                    "b6462cd0-37aa-4e3f-a4d6-78dcc94a9685",
                    "pay"
                  ]
                }
              },
              "response": []
            }
          ]
        },
        {
          "name": "пиццы",
          "item": [
            {
              "name": "Список пицц",
              "request": {
                "method": "GET",
                "header": [],
                "url": {
                  "raw": "{{pizzaURL}}/api/pizzas",
                  "host": [
                    "{{pizzaURL}}"
                  ],
                  "path": [
                    "api",
                    "pizzas"
                  ]
                }
              },
              "response": []
            },
            {
              "name": "Получение пиццы по id",
              "request": {
                "method": "GET",
                "header": [],
                "url": {
                  "raw": "{{pizzaURL}}/api/pizzas/6ac6a243-e36f-45d9-b371-5a33346b1321?withImages=true",
                  "host": [
                    "{{pizzaURL}}"
                  ],
                  "path": [
                    "api",
                    "pizzas",
                    "6ac6a243-e36f-45d9-b371-5a33346b1321"
                  ],
                  "query": [
                    {
                      "key": "withImages",
                      "value": "true"
                    }
                  ]
                }
              },
              "response": []
            },
            {
              "name": "Список размеров",
              "request": {
                "method": "GET",
                "header": [],
                "url": {
                  "raw": "{{pizzaURL}}/api/pizza-sizes",
                  "host": [
                    "{{pizzaURL}}"
                  ],
                  "path": [
                    "api",
                    "pizza-sizes"
                  ]
                }
              },
              "response": []
            }
          ]
        }
      ]
    },
    {
      "name": "Запросы под admin",
      "item": [
        {
          "name": "Данны о всех заказах",
          "request": {
            "method": "GET",
            "header": []
          },
          "response": []
        },
        {
          "name": "Создание пиццы",
          "request": {
            "method": "POST",
            "header": [],
            "body": {
              "mode": "raw",
              "raw": "{\n    \"name\": \"САВАПИЦЦЫ\",\n    \"price\": \"777\",\n    \"description\": \"ПУСТАЯ\",\n    \"image_base64\": \"ццц\",\n    \"size_id\": \"7414e8f1-981a-40ae-9ce1-e036d74efb81\"\n}",
              "options": {
                "raw": {
                  "language": "json"
                }
              }
            },
            "url": {
              "raw": "{{pizzaURL}}/api/admin/pizzas",
              "host": [
                "{{pizzaURL}}"
              ],
              "path": [
                "api",
                "admin",
                "pizzas"
              ]
            }
          },
          "response": []
        },
        {
          "name": "Изменение пиццы",
          "request": {
            "method": "PUT",
            "header": [],
            "body": {
              "mode": "raw",
              "raw": "{\n    \"name\": \"САВАПИЦЦЫ\",\n    \"price\": \"777\",\n    \"description\": \"ПУСТАЯ\",\n    \"image_base64\": \"ццц\",\n    \"size_id\": \"7414e8f1-981a-40ae-9ce1-e036d74efb81\"\n}"
            },
            "url": {
              "raw": "{{pizzaURL}}/api/admin/pizzas/61a87159-16c0-4673-8ca0-34b9f79c55b6",
              "host": [
                "{{pizzaURL}}"
              ],
              "path": [
                "api",
                "admin",
                "pizzas",
                "61a87159-16c0-4673-8ca0-34b9f79c55b6"
              ]
            }
          },
          "response": []
        },
        {
          "name": "Удаление пиццы",
          "request": {
            "method": "DELETE",
            "header": [],
            "url": {
              "raw": "{{pizzaURL}}/api/admin/pizzas/8368d6f9-ca31-4766-9653-431179f9f259",
              "host": [
                "{{pizzaURL}}"
              ],
              "path": [
                "api",
                "admin",
                "pizzas",
                "8368d6f9-ca31-4766-9653-431179f9f259"
              ]
            }
          },
          "response": []
        },
        {
          "name": "Инфо о всех заказах",
          "protocolProfileBehavior": {
            "disableBodyPruning": true
          },
          "request": {
            "method": "GET",
            "header": [],
            "body": {
              "mode": "raw",
              "raw": ""
            },
            "url": {
              "raw": "{{pizzaURL}}/api/admin/orders",
              "host": [
                "{{pizzaURL}}"
              ],
              "path": [
                "api",
                "admin",
                "orders"
              ]
            }
          },
          "response": []
        },
        {
          "name": "Удаление заказа",
          "request": {
            "method": "DELETE",
            "header": [],
            "url": {
              "raw": "{{pizzaURL}}/api/admin/orders/220062b6-8d3d-4432-8031-d108f798a5bf",
              "host": [
                "{{pizzaURL}}"
              ],
              "path": [
                "api",
                "admin",
                "orders",
                "220062b6-8d3d-4432-8031-d108f798a5bf"
              ]
            }
          },
          "response": []
        }
      ]
    }
  ],
  "auth": {
    "type": "bearer",
    "bearer": [
      {
        "key": "token",
        "value": "5a421c65-60cf-45fd-bf84-4de193194798",
        "type": "string"
      }
    ]
  },
  "event": [
    {
      "listen": "prerequest",
      "script": {
        "type": "text/javascript",
        "packages": {},
        "requests": {},
        "exec": [
          ""
        ]
      }
    },
    {
      "listen": "test",
      "script": {
        "type": "text/javascript",
        "packages": {},
        "requests": {},
        "exec": [
          ""
        ]
      }
    }
  ],
  "variable": [
    {
      "key": "pizzaURL",
      "value": ""
    }
  ]
}
