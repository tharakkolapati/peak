package com.test;

import java.util.*;

public class EmpPriceDist {

	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		System.out.print("Enter Number of the employees : ");
		int n = sc.nextInt();
		int[] priceArray = new int[10];
		Map<Integer, String> prices = new TreeMap<Integer, String>();
		prices.put(7980, "Fitbit Plus");
		prices.put(22349, "IPods");
		prices.put(999, "MI Band");
		prices.put(2799, "Cult Pass");
		prices.put(229900, "Macbook Pro");
		prices.put(11101, "Digital Camera");
		prices.put(9999, "Alexa");
		prices.put(2195, "Sandwich Toaster");
		prices.put(9800, "Microwave Oven");
		prices.put(4999, "Scale");
		// System.out.println(prices);
		int size = 0;
		for (Map.Entry<Integer, String> p : prices.entrySet()) {

			priceArray[size] = p.getKey();
			// System.out.println("price"+size+"value"+priceArray[size]);
			size++;
		}

		int result = priceArray[size - 1] - priceArray[0];
		int firstprice = 0, lastPrice = 0;
		for (int i = 0, j = n - 1; i < size - n && j < size; i++, j++) {
			if (priceArray[j] - priceArray[i] < result) {
				result = priceArray[j] - priceArray[i];
				firstprice = i;
				lastPrice = j;
				// System.out.println(lastPrice+"lastPrice"+"/nfirstprice"+firstprice+"/nresult"+result);
			}
		}
		System.out.println("Here the goodies that are selected for distribution are:");
		for (int temp = firstprice; temp <= lastPrice; temp++) {

			System.out.println(prices.get(priceArray[temp]) + " : " + priceArray[temp]);
		}
		System.out.println("\r\n"
				+ "And the difference between the chosen goodie with highest price and the lowest price is " + result);
	}
}
