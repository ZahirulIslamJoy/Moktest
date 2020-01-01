FORMAT: 1A
HOST: https://polls.apiblueprint.org/

# Campus_api

Building a restful api for creating, updating, retrieving or deleting users information.

## Users [/campus/user]

### List All Users [GET]

To see the list of the users 

+ Response 200 (application/json)


        [
            {
                "status": "success",
                "result": 2,
                "data": {
                    "users": [
                        {
                            "_id": "5e0ca8cc3aab1f6d0f0d06ba",
                            "name": "Zahirul Islam Joy",
                             "phone": "01733850321",
                             "roll": 128,
                            "__v": 0
                        },
                        {
                           "_id": "5e0cac193aab1f6d0f0d06bc",
                            "name": "Rifat",
                            "phone": "01732225032",
                             "roll": 120,
                            "__v": 0
                        }
                    ]
                }
            }
        ]

### Entering data of new User [POST]
we can add new user through this.so we need 3 perameters
1.name
2.phone
3.roll


+ Request (application/json)
    
        {
            "Name": "Rifat",
            "phone": "01732225032",
            "roll": "120"
        }

+ Response 201 (application/json)

    + Headers

            Location: 127.0.0.1:4000/campus/user

    + Body

            {
                "status": "success",
                "data": {
                    "newUser": {
                        "_id": "5e0caf623aab1f6d0f0d06be",
                         "name": "Rifat",
                        "phone": "01732225032",
                        "roll": 120,
                        "__v": 0
                    }
                }
            }
            
### Update an Existing User [PATCH]

we can update the information through this action.To update information we just need the id

Now i will use this id : 5e0caf623aab1f6d0f0d06be

+ Request (application/json)

        {
             "name": "sifat",
            "phone":"01732225032",
            "roll":120
        }

+ Response 200 (application/json)

    + Headers

            Location: 127.0.0.1:4000/campus/user/5e0caf623aab1f6d0f0d06be

    + Body

            {
                "status": "success",
                "data": {
                    "user": {
                        "_id": "5e0cac193aab1f6d0f0d06bc",
                        "name": "sifat",
                        "phone": "01732225032",
                        "roll": 120,
                         "__v": 0
                    }
                }
            }
            
### Delete an Existing User [DELETE]

Through this action we can delete an exciting information.so we need user id to do this action
 now i will Use this  id: 5e0c7b04beae0b2f386e206e

+ Request (application/json)

        {
            "name": "sifat",
            "phone":"01732225032",
            "roll":120
        }


+ Response 200 (application/json)

    + Headers

            Location: 127.0.0.1:4000/campus/user/5e0caf623aab1f6d0f0d06be

    + Body

            {
                "message": "204 No content"
            }
