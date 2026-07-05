文字列の先頭10文字を日付部分として扱えば十分です。

```dart
Map<String, int> countByDate(List<String> isoDateTimes) {
  final counts = <String, int>{};

  for (final dateTime in isoDateTimes) {
    final date = dateTime.substring(0, 10); // yyyy-MM-dd
    counts[date] = (counts[date] ?? 0) + 1;
  }

  return counts;
}
```

使用例です。

```dart
void main() {
  final list = [
    '2026-07-05T10:30:00',
    '2026-07-05T23:59:59',
    '2026-07-06T00:00:00',
  ];

  final result = countByDate(list);

  print(result);
  // {2026-07-05: 2, 2026-07-06: 1}
}
```

入力が必ずISO8601形式で、少なくとも `yyyy-MM-dd` まで含む前提ならこれで問題ありません。
