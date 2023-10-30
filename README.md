#! /bin/bash
# cars.sh
# [Your Name Here]

while true
do
    echo "Menu Options:"
    echo "1) Add a car"
    echo "2) List the cars in the inventory file"
    echo "3) Quit the program"
    echo ""
    read -p "Enter your choice (1-3): " CHOICE

    case $CHOICE in
        1)
            read -p "Enter year of the car: " YEAR
            read -p "Enter make of the car: " MAKE
            read -p "Enter model of the car: " MODEL
            echo "$YEAR:$MAKE:$MODEL" >> My_old_cars
            ;;

        2)
            echo "Listing all cars:"
            sort -t : -k 1 My_old_cars
            ;;

        3)
            echo "Goodbye!"
            exit
            ;;

        *)
            echo "Invalid choice. Please choose a number between 1 and 3."
            ;;
    esac
done
