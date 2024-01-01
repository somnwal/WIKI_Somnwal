# ViewBinding

### build.gradle

```gradle
buildFeatures {
    viewBinding true
}
```

### 액티비티

```kotlin
private ActivityMainBinding binding;

@Override
protected void onCreate(Bundle savedInstanceState) {
	super.onCreate(savedInstanceState);
	binding = ActivityMainBinding.inflate(getLayoutInflater());
	setContentView(binding.getRoot());
}
```

### 프래그먼트

```kotlin
class HomeFragment : Fragment() {

    lateinit var binding: FragmentHomeBinding

    override fun onCreateView(
        inflater: LayoutInflater,
        container: ViewGroup?,
        savedInstanceState: Bundle?
    ): View {
        binding = FragmentInternalBinding.inflate(inflater, container, false)
        return binding.root
    }
}
```

\
