![image](https://github.com/Nasshor01/2DPlatformer/assets/141824772/3ba468e9-d92e-41da-bdfa-e3cfb70c765f)

EnhancedInputAction IA_Move
  -> Action Value X
  -> Multiply (X: Action Value X, Y: -1)
  -> Make Vector (X: Multiply Output, Y: 0, Z: 0)
  -> Add Movement Input (Target: Self, World Direction: Make Vector Output, Scale Value: 1.0)
