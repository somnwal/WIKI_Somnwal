# AlertDialog (Positive/Negative)

## Dialog

### Alert Dialog (Positive / Negative)

```kotlin
val builder = AlertDialog.Builder(this)

                builder.setTitle("삭제 확인")
                    .setMessage("삭제하시겠습니까?")
                    .setPositiveButton("예",
                    DialogInterface.OnClickListener { dialog, id ->
                    // TODO()
                }).setNegativeButton("아니오",
                    DialogInterface.OnClickListener { dialog, id ->
                    // TODO()
                })
                
                val dialog = builder.create()
                dialog.show()
```

\
