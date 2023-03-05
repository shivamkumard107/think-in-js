## Functional
1. Display Product
2. Add / Remove Product (Retailer)
3. Add to cart (Customer)
4. Review Product
5. Wishlist/Like Product
6. Place the Order
7. Search a Product
8. Tracking an Order

## Non functional Requirements
1. Highly Scalable
2. Available
3. Secure
4. Consistency

## High Level Design (HLD)
[[E-commerce HLD.canvas]]

## Vertical Vs Horizontail Scaling
Horizontal scaling means scaling by **adding more machines** to your pool of resources (also described as **"scaling out"**), whereas vertical scaling refers to scaling by **adding more power** (e.g. CPU, RAM) to an existing machine (also described as **"scaling up"**).

## Consistent Hashing
Consistent Hashing is a distributed hashing scheme that operates independently of the number of servers or objects in a distributed hash table by assigning them a position on an abstract circle, or hash ring. This allows servers and objects to scale without affecting the overall system.

## Message Queues
1. Kafka
2. SQS- Simple Queue Service

## Linting
Linting is a tool for identifying and reporting on patterns found in code, with the goal of making code more consistent and avoiding bugs. We'll use *ESlint*  in our project for EcmaScript/Javascript code
`npm init @eslint/config`

## Winston
A multi-transport async logging library for Node.js
