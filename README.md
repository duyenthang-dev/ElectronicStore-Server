# Mock server cho electronic store front end
- Base Url: https://mock-electronic-server.herokuapp.com/api/
<h2>Từ phía client dùng fetch hoặc axios gọi tới end point để lấy data</h2>
<h3> Để lấy danh sách sản phẩm  </h3>

```js
import axios from "axios"
import queryString from "query-string"
 
const axiosClient = axios.create({
   baseURL: "https://mock-electronic-server.herokuapp.com/api",
   headers: {
      "content-type": "application/json",
   },
   paramsSerializer: (params) => queryString.stringify(params),
})  
 
useEffect(() => {
   axiosClient.get(`/products`).then((response) => {
      console.log(response.data)
   })
}, [])
 ```
### Kết quả sẽ trả về một danh sách sản phẩm có dạng
```js
{
  "id": 2,
  "name": "Samsung Galaxy S22 8/256GB Chính Hãng",
  "type": "Samsung",
  "quantity": 99,
  "market_price": 21500000,
  "discount_price": 18000000,
  "sizeList": [
      128,
      256
  ],
  "colorList": [
    "White",
    "Yellow",
    "Green",
    "Pink"
  ],
  "short_description": "Samsung Galaxy S22 sở hữu thiết kế tinh tế cùng hiệu năng mạnh mẽ với sự xuất hiện của con chip Qualcom Snapdragon 8 Gen 1 8 nhân đem đến nhiều cải tiến    về sức mạnh xử lý cũng như chất lượng chụp hình từ camera.",
  "categoryId": 1,
  "features": [
      "finger",
      "faceId",
      "warerProof",
      "quickCharge"
  ],
   "screen": "largeScreen",
  "rating_average": 4.4,
  "review_count": 100,
  "sell_count": 235,
  "imageList": [
      "https://i.ibb.co/sQxVWn5/samsung-s22-pink.webp",
      "https://i.ibb.co/WyGq2hv/samsung-s22-black.webp",
      "https://i.ibb.co/tP977QT/samsung-s22-green.webp",
      "https://i.ibb.co/GRGXDvS/samsung-s22-white.webp"
   ]
}
```
