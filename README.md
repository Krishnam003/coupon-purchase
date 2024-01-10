# CouponPurchase

## Overview

The CouponPurchase smart contract is a Solidity contract designed to facilitate the purchase and application of coupons for discounts on specified amounts. Users can purchase coupons with a discount percentage, and once purchased, they can apply the coupon to reduce the cost of future transactions.

## Features

1. **Purchase Coupon:**
   - Users can purchase coupons by calling the `purchaseCoupon` function, specifying the desired discount percentage.
   - The discount should be between 1% and 50%.

2. **Apply Coupon:**
   - After purchasing a coupon, users can apply it to a specified amount using the `applyCoupon` function.
   - The discounted amount is calculated based on the coupon's percentage.

3. **Coupon Selling:**
   - Admin or other users can sell coupons to a specified buyer using the `sellCoupon` function.
   - The buyer must not have an existing coupon.

## Contract Details

### State Variables

- `adminAddress`: The address of the contract administrator.
- `hasPurchasedCoupon`: A mapping to track whether an address has purchased a coupon.
- `couponDiscounts`: A mapping to store the discount percentage associated with each address.

### Events

- `CouponPurchased`: Triggered when a coupon is purchased. Logs the buyer's address and the discount percentage.
- `DiscountApplied`: Triggered when a coupon is applied. Logs the user's address, the original amount, and the discounted amount.

### Functions

- **Constructor:**
  - Initializes the contract with the deployer's address as the administrator.

- **purchaseCoupon:**
  - Allows users to purchase a coupon with a specified discount percentage.
  - Ensures the discount is between 1% and 50%.
  - Checks if the user has already purchased a coupon.

- **applyCoupon:**
  - Allows users to apply a purchased coupon to a specified amount.
  - Checks if the user has purchased a coupon.
  - Calculates the discounted amount based on the coupon percentage.

- **sellCoupon:**
  - Allows the administrator or other users to sell a coupon to a specified buyer.
  - Ensures the discount is between 1% and 50%.
  - Checks if the buyer already has a coupon.

## Usage

1. **Deploy Contract:**
   - Deploy the `CouponPurchase` contract, and the deployer's address becomes the administrator.

2. **Purchase Coupon:**
   - Users can call the `purchaseCoupon` function to buy a coupon with a specified discount.

3. **Apply Coupon:**
   - Purchasers can then use the `applyCoupon` function to apply the purchased coupon and get a discounted amount.

4. **Sell Coupon:**
   - The administrator or other users can use the `sellCoupon` function to sell a coupon to a specified buyer.

## Author

km1522771@gmail.com

## License

This smart contract is released under the MIT License. See the SPDX-License-Identifier at the top of the contract file for details.
