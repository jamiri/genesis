# Slice.Split

```go
func (s Slice) Split(sep T) [][]T
```

Split splits arr by sep

Generic types: T.

## Structs

| Struct | T type |
| ------ | ------ |
| SliceBool | bool |
| SliceByte | byte |
| SliceString | string |
| SliceFloat32 | float32 |
| SliceFloat64 | float64 |
| SliceInt | int |
| SliceInt8 | int8 |
| SliceInt16 | int16 |
| SliceInt32 | int32 |
| SliceInt64 | int64 |
| SliceUint | uint |
| SliceUint8 | uint8 |
| SliceUint16 | uint16 |
| SliceUint32 | uint32 |
| SliceUint64 | uint64 |
| SliceInterface | interface{} |

## Source

```go
// Split splits arr by sep
func (s Slice) Split(sep T) [][]T {
	result := make([][]T, 0)
	curr := make([]T, 0)
	for _, el := range s.Data {
		if el == sep {
			result = append(result, curr)
		} else {
			curr = append(curr, el)
		}
	}
	result = append(result, curr)
	return result
}
```
