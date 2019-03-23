# FishingBoat

import java.util.Scanner;

public class P38_FishingBoat {

    public static void main(String[] args) {
        Scanner var_scan = new Scanner(System.in);
        int budget = Integer.parseInt(var_scan.nextLine());
        String season = var_scan.nextLine();
        int fishersCount = var_scan.nextByte();

        double rentPrice = 0;

        if (season.equalsIgnoreCase("Spring")) {
            if (fishersCount <= 6) {
                rentPrice = 3000 - 0.1 * 3000;
            } else if (fishersCount <= 11) {
                rentPrice = 3000 - 0.15 * 3000;
            } else {
                rentPrice = 3000 - 0.25 * 3000;
            }

        } else if (season.equalsIgnoreCase("Summer")) {
            if (fishersCount <= 6) {
                rentPrice = 4200 - 0.1 * 4200;
            } else if (fishersCount <= 11) {
                rentPrice = 4200 - 0.15 * 4200;
            } else {
                rentPrice = 4200 - 0.25 * 4200;
            }

        } else if (season.equalsIgnoreCase("Autumn")) {
            if (fishersCount <= 6) {
                rentPrice = 4200 - 0.1 * 4200;
            } else if (fishersCount <= 11) {
                rentPrice = 4200 - 0.15 * 4200;
            } else {
                rentPrice = 4200 - 0.25 * 4200;
            }
        } else if (season.equalsIgnoreCase("Winter")) {
            if (fishersCount <= 6) {
                rentPrice = 2600 - 0.1 * 2600;
            } else if (fishersCount <= 11) {
                rentPrice = 2600 - 0.15 * 2600;
            } else {
                rentPrice = 2600 - 0.25 * 2600;
            }
        }
        if (fishersCount % 2 == 0 && !(season.equalsIgnoreCase("Autumn"))) {
            rentPrice = rentPrice - 0.05 * rentPrice;
        }
        if (budget >= rentPrice){
            double moneyLeft = budget - rentPrice;
            System.out.printf("Yes! You have %.2f leva left.", moneyLeft);
        } else {
            double neededMoney = rentPrice - budget;
            System.out.printf("Not enough money! You need %.2f leva.", neededMoney);
        }
    }

}
