## complete_path
* greet
    - utter_greet
* restaurant_search
    - utter_ask_location
* restaurant_search{"location": "Bengaluru"}
    - slot{"location": "Bengaluru"}
    - utter_ask_cuisine
* restaurant_search{"cuisine": "Chinese"}
    - slot{"cuisine": "Chinese"}
    - utter_ask_price
* restaurant_search{"price": "mid"}
    - slot{"price": "mid"}
    - action_search_restaurants
    - utter_email_prompt
* affirm
    - utter_ask_email
* email{"email": "pyemailrasa@gmail.com"}
    - slot{"email": "pyemailrasa@gmail.com"}
    - action_send_email
* goodbye
    - utter_goodbye

## no_interaction
* greet
    - utter_greet
* goodbye
    - utter_goodbye

## location_specified
* greet
    - utter_greet
* restaurant_search{"location": "Delhi"}
    - slot{"location": "Delhi"}
    - action_check_location
    - utter_ask_cuisine
* restaurant_search{"cuisine": "North Indian"}
    - slot{"cuisine": "North Indian"}
    - utter_ask_price
* restaurant_search{"price": "mid"}
    - slot{"price": "mid"}
    - action_search_restaurants
    - slot{"location": "Delhi"}
    - utter_email_prompt
* email{"email" : "pyemailrasa@gmail.com"}
    - slot{"email" : "pyemailrasa@gmail.com"}
    - action_send_email
    - reset_slots
    - utter_goodbye

## worng_location_specified
* greet
    - utter_greet
* restaurant_search{"location": "rishikesh"}
    - slot{"location": "rishikesh"}
    - action_check_location
    - utter_ask_location
* restaurant_search{"location": "kannur"}
    - slot{"location": "kannur"}
    - action_check_location
    - utter_ask_cuisine
* restaurant_search{"cuisine": "Chinese"}
    - slot{"cuisine": "Chinese"}
    - utter_ask_price
* restaurant_search{"price": "high"}
    - slot{"price": "high"}
    - action_search_restaurants
    - slot{"location": "kannur"}
    - utter_email_prompt
    - utter_goodbye
