## Get all companies

> Response body | `HTTP 200`

```JSON
# GET /articles/companies?page[size]=2

{
    "data": [
        {
            "id": "1",
            "type": "companies",
            "attributes": {
                "display_title": "Amstrad",
                "sort_title": "Amstrad",
                "slug": "amstrad",
                "description": "Amstrad is a British electronics company best known within gaming as creator of the Amstrad 464 and CPC home computers of the 1980s.",
                "last_review_outcome": null,
                "last_review_comments": null,
                "origin_date": null,
                "origin_year": 1968,
                "ended": null,
                "end_date": null,
                "end_year": null
            },
            "relationships": {
                "primary_image": {
                    "data": null,
                    "links": {
                        "related": "http://localhost:3000/media/images/23"
                    }
                },
                "created_by": {
                    "data": {
                        "id": "1",
                        "type": "users"
                    },
                    "links": {
                        "related": "http://localhost:3000/users/1"
                    }
                },
                "last_reviewed_by": {
                    "data": null
                },
                "origin_place": {
                    "data": {
                        "id": "1031",
                        "type": "places"
                    },
                    "links": {
                        "related": "http://localhost:3000/places/1031"
                    }
                },
                "latest_place": {
                    "data": null,
                    "links": {
                        "related": "http://localhost:3000/places/2937"
                    }
                },
                "names": {
                    "data": [
                        {
                            "id": "1",
                            "type": "company_names"
                        }
                    ],
                    "links": {
                        "related": "http://localhost:3000/articles/companies/1/names"
                    },
                    "meta": {
                        "total": 1
                    }
                },
                "notes": {
                    "data": [],
                    "links": {
                        "related": "http://localhost:3000/articles/companies/1/notes"
                    },
                    "meta": {
                        "total": 0
                    }
                },
                "images": {
                    "data": [],
                    "links": {
                        "related": "http://localhost:3000/articles/companies/1/images"
                    },
                    "meta": {
                        "total": 0
                    }
                },
                "credits": {
                    "data": [],
                    "links": {
                        "related": "http://localhost:3000/articles/companies/1/credits"
                    },
                    "meta": {
                        "total": 0
                    }
                },
                "parents": {
                    "data": [],
                    "links": {
                        "related": "http://localhost:3000/articles/companies/1/parents"
                    },
                    "meta": {
                        "total": 0
                    }
                },
                "children": {
                    "data": [],
                    "links": {
                        "related": "http://localhost:3000/articles/companies/1/children"
                    },
                    "meta": {
                        "total": 0
                    }
                },
                "platforms": {
                    "data": [
                        {
                            "id": "1",
                            "type": "platforms"
                        },
                        {
                            "id": "2",
                            "type": "platforms"
                        }
                    ],
                    "links": {
                        "related": "http://localhost:3000/platforms?filter%5Bholder_id%5D=1"
                    },
                    "meta": {
                        "total": 2
                    }
                }
            },
            "links": {
                "self": "http://localhost:3000/articles/companies/1"
            },
            "meta": {
                "created_at": "2017-08-25T08:32:15.415Z",
                "updated_at": "2017-08-25T08:32:15.415Z",
                "meta_description": "Find Amstrad's game credits, profile, images and facts at Dbljump, the video game reference.",
                "meta_keywords": "Amstrad, 1968, London, United Kingdom, company, profile, biography, trivia, dbljump, video games, pc games, gaming",
                "status": "published",
                "last_submitted_at": null,
                "last_reviewed_at": null,
                "published_at": "2017-08-25T08:32:15.329Z",
                "total_names": 1,
                "total_notes": 0,
                "total_images": 0,
                "total_credits": 0,
                "total_parents": 0,
                "total_children": 0
            }
        },
        {
            "id": "2",
            "type": "companies",
            "attributes": {
                "display_title": "Sinclair Research Ltd",
                "sort_title": "Sinclair Research Ltd",
                "slug": "sinclair-research-ltd",
                "description": "Sinclair Research is a British electronics company best known within gaming as creator of the ZX Spectrum series of home computers.",
                "last_review_outcome": null,
                "last_review_comments": null,
                "origin_date": null,
                "origin_year": 1973,
                "ended": null,
                "end_date": null,
                "end_year": null
            },
            "relationships": {
                "primary_image": {
                    "data": null,
                    "links": {
                        "related": "http://localhost:3000/media/images/23"
                    }
                },
                "created_by": {
                    "data": {
                        "id": "1",
                        "type": "users"
                    },
                    "links": {
                        "related": "http://localhost:3000/users/1"
                    }
                },
                "last_reviewed_by": {
                    "data": null
                },
                "origin_place": {
                    "data": {
                        "id": "2925",
                        "type": "places"
                    },
                    "links": {
                        "related": "http://localhost:3000/places/2925"
                    }
                },
                "latest_place": {
                    "data": {
                        "id": "1031",
                        "type": "places"
                    },
                    "links": {
                        "related": "http://localhost:3000/places/1031"
                    }
                },
                "names": {
                    "data": [
                        {
                            "id": "2",
                            "type": "company_names"
                        }
                    ],
                    "links": {
                        "related": "http://localhost:3000/articles/companies/2/names"
                    },
                    "meta": {
                        "total": 1
                    }
                },
                "notes": {
                    "data": [],
                    "links": {
                        "related": "http://localhost:3000/articles/companies/2/notes"
                    },
                    "meta": {
                        "total": 0
                    }
                },
                "images": {
                    "data": [],
                    "links": {
                        "related": "http://localhost:3000/articles/companies/2/images"
                    },
                    "meta": {
                        "total": 0
                    }
                },
                "credits": {
                    "data": [],
                    "links": {
                        "related": "http://localhost:3000/articles/companies/2/credits"
                    },
                    "meta": {
                        "total": 0
                    }
                },
                "parents": {
                    "data": [],
                    "links": {
                        "related": "http://localhost:3000/articles/companies/2/parents"
                    },
                    "meta": {
                        "total": 0
                    }
                },
                "children": {
                    "data": [],
                    "links": {
                        "related": "http://localhost:3000/articles/companies/2/children"
                    },
                    "meta": {
                        "total": 0
                    }
                },
                "platforms": {
                    "data": [
                        {
                            "id": "3",
                            "type": "platforms"
                        }
                    ],
                    "links": {
                        "related": "http://localhost:3000/platforms?filter%5Bholder_id%5D=2"
                    },
                    "meta": {
                        "total": 1
                    }
                }
            },
            "links": {
                "self": "http://localhost:3000/articles/companies/2"
            },
            "meta": {
                "created_at": "2017-08-25T08:32:15.514Z",
                "updated_at": "2017-08-25T08:32:15.514Z",
                "meta_description": "Find Sinclair Research Ltd's game credits, profile, images and facts at Dbljump, the video game reference.",
                "meta_keywords": "Sinclair Research Ltd, 1973, Cambridge, East of England, United Kingdom, London, United Kingdom, company, profile, biography, trivia, dbljump, video games, pc games, gaming",
                "status": "published",
                "last_submitted_at": null,
                "last_reviewed_at": null,
                "published_at": "2017-08-25T08:32:15.460Z",
                "total_names": 1,
                "total_notes": 0,
                "total_images": 0,
                "total_credits": 0,
                "total_parents": 0,
                "total_children": 0
            }
        }
    ],
    "links": {
        "self": "http://localhost:3000/articles/companies?page%5Bnumber%5D=1&page%5Bsize%5D=2",
        "next": "http://localhost:3000/articles/companies?page%5Bnumber%5D=2&page%5Bsize%5D=2",
        "last": "http://localhost:3000/articles/companies?page%5Bnumber%5D=26&page%5Bsize%5D=2"
    },
    "meta": {
        "total_items": 52
    }
```

Retrieve all company articles. Automatically paginated.

* User authentication: not required
* Authorization level: n/a

### HTTP request

`GET /articles/companies`

### URL query parameters

Parameter | Default | Description
--------- | ------- | -----------
fields[{record-type}] | All fields | Return only specified fields, e.g. `?fields[companies]=display_title,description`
filter[{field}] | All records | Filter search by field, e.g. `?filter[end]=true`
page[number] | 1 | Select the page number, e.g. `?page[number]=3`
page[size] | 30 | Select the number of records per page, e.g. `?page[size]=20`

### Success HTTP response code

`200 OK`
