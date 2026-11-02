# 用于差分电荷分析的三套总电子密度

这些是组成差分的三个总电子密度CUBE，均已做SPIN1+SPIN2，并非三个不同的差分密度：

- 01_interface_total.cube：完整LRM/LPO界面，192原子。
- 02_LRM_frozen_total.cube：固定在界面位置的LRM片段，97原子。
- 03_LPO_frozen_total.cube：固定在界面位置的LPO片段，95原子。

差分定义：Δρ = 01 − 02 − 03。
已经相减完成的文件在上一级目录delta_rho.cube，直接打开即可绘制。

三文件使用相同晶胞、原点和480×125×216网格，未平移、重采样或平滑。
坐标和网格向量单位Bohr；体数据单位电子/Bohr³。不是SPIN1−SPIN2的磁化密度。

等值面±0.003 e/Å³等于±0.000444554 e/Bohr³。导入VESTA时应依据显示的体数据单位设置等值面；若软件已自动转换为e/Å³，就使用±0.003。不要重复换算。

manifest.json提供积分电子数、原始自旋文件路径、文件哈希及回读验证结果。

## 已完成 VESTA 原生绘图

- delta_rho_final.vesta：本机 VESTA 保存的可编辑工程，包含旋转、缩放和等值面设置。该工程引用上一级差分 CUBE 的本机绝对路径；移动文件时需重新指定密度文件。
- vesta_charge_difference.png：由 VESTA -export_img 原生导出的预览，不是 Python 渲染图。
- 已通过 VESTA 的体数据最小/最大值与原始 CUBE 对照，确认本次导入的密度保持 e/Bohr³。Isosurface level 使用 0.000444554，并显示正负等值面，对应 ±0.003 e/Å³。
- 原生项目保留 VESTA 默认原子颜色及边界截面显示，可继续调整颜色、透明度、边界和视角。
