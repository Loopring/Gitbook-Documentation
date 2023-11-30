# Get collections by contract address

Get collections info by contract address, may return multiple collections.

## Endpoint

GET **/api/v3/nft/public/collections**

***

## **Request**

|   Query Param   | Description                         | Example                                    |
| :-------------: | ----------------------------------- | ------------------------------------------ |
| contractAddress | Token address collection related to | 0xca98c604645bca84283da1b773335302359bbe81 |
|      offset     | (Optional)                          | 0                                          |
|      limit      | (Optional)                          | 20                                         |

## **Response**

See [Collection](../list-owned-collections/#collection)

***

