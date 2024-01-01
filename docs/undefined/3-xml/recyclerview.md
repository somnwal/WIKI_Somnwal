# RecyclerView

### RecyclerView

#### ViewHolder Class

ViewHolder 클래스에 칸별로 iterate할 항목들을 적어준다.

```kotlin
class PdfViewHolder(itemView: View) : RecyclerView.ViewHolder(itemView) {

    var tvName: TextView
    var container: CardView

    init {
        tvName = itemView.findViewById(R.id.textPdfName)
        container = itemView.findViewById(R.id.container)

    }

}
```

