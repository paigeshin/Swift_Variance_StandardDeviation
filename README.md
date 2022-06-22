# Swift_Variance_StandardDeviation

```swift

    static func average(data: [Double]) -> Double {
        if data.count == 0 || data.count < 0 {
            return 0
        }
        let sum = data.reduce(0) {$0 + $1}
        return sum / Double(data.count)
    }
    
    static func variance(data: [Double]) -> Double {
        if data.count == 0 || data.count < 0 {
            return 0
        }
        let sum = data.reduce(0) {$0 + $1}
        let median = sum / Double(data.count)
        var variance: Double = 0
        data.forEach { value in
            variance += (value - median) * (value - median)
        }
        variance = variance / Double(data.count)
        return variance
    }
    
    static func standardDeviation(data: [Double]) -> Double {
        let length = Double(data.count)
        let avg = data.reduce(0, {$0 + $1}) / length
        let sumOfSquaredAvgDiff = data.map { pow($0 - avg, 2.0)}.reduce(0, {$0 + $1})
        return sqrt(sumOfSquaredAvgDiff / length)
    }


```
