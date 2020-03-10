## recommender-system-collaborative-filtering-knn
### That is a recommender system (collaborative filtering) with python from scratch

#### we use a simple dataset like it
```python
users = {"user0": {
            "car": 0.0,
            "bike": 0.0,
            "motorcycle": 0.0,
            "skirt": 0.0,
            "hat": 0.0,
            "pants": 0.0,
            "banana": 0.0,
            "cucumber": 0.0,
            "carrots": 0.0,
            "tomato": 0.0,
            "iPhone": 5.0,
            "iPad": 0.0,
            "iMac": 0.0,
            "bag": 0.0,
            "book": 0.0,
            "pen": 0.0,
            "pencil": 0.0,
            "eraser": 0.0,
            "laptop": 0.0,
            "computer ": 0.0,
            "computer mouse": 0.0,
            "phone": 0.0,
            "guitar": 0.0,
            "piano": 0.0,
            "violin": 0.0,
            "sound card": 0.0,
            "music": 0.0,
        },

        "user1": {
            "car": 5.0,
            "bike": 3.0,
            "motorcycle": 3.0,
            "skirt": 0.0,
            "hat": 0.0,
            "pants": 0.0,
            "banana": 0.0,
            "cucumber": 0.0,
            "carrots": 0.0,
            "tomato": 0.0,
            "iPhone": 0.0,
            "iPad": 0.0,
            "iMac": 0.0,
            "bag": 0.0,
            "book": 0.0,
            "pen": 0.0,
            "pencil": 0.0,
            "eraser": 0.0,
            "laptop": 2.0,
            "computer ": 2.0,
            "computer mouse": 0.0,
            "phone": 0.0,
            "guitar": 0.0,
            "piano": 0.0,
            "violin": 0.0,
            "sound card": 0.0,
            "music": 1.0,
        },
..........

```


#### and for finding nearest neighbors i use CosineSimilarity and Manhattan and you can choose one of them
```python
    def manhattan(self, rating1, rating2):
        distance = 0
        for key in rating1:
            if key in rating2:
                distance += abs(rating1[key] - rating2[key])
        return distance

    def cosineSimilarity(self, rating1, rating2):
        zigma_x2 = 0
        zigma_y2 = 0

        for oneRate in rating1:
            zigma_x2 = zigma_x2 + rating1[oneRate] * rating1[oneRate] 
        sum_x2_sqrt = sqrt(zigma_x2) 

        for oneRate in rating2:
            zigma_y2 = zigma_y2 + rating2[oneRate] * rating2[oneRate] 
        sum_y2_sqrt = sqrt(zigma_y2) 

        multi = 0
        for product in rating1:
            if product in rating2:
                multi = multi + rating2[product] * rating1[product]
        
        distance = multi / (sum_x2_sqrt * sum_y2_sqrt)
        distance = distance * -1 
        return distance
```
#### and you can use is simple with make an object and call recommender function

```python
# Manhattan is type 1
# CosineSimilarity is type 2
# myRecommender = recommender("That is you seed data", "that is k", "that is the count of results", "that is the type of algorithm")
myRecommender = recommender(users, 3, 3, 2)
# myRecommender.recommend("Which user that you want to make recommend for him")
myRecommender.recommend("user0")
```

## :))
