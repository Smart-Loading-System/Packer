# Packer
scripts for packing boxes to any limited cuboid space, like pallet or container

Source files are input.xlsx and colors.xlsx
input.xlsx - essential data about boxes we need to pack, quantity and box_templates

Master Data sheet contains 3 mandatory columns
![image](https://user-images.githubusercontent.com/102654728/174077696-3a1d8e10-35c8-4b96-9110-a873e2b23e3e.png)

Sheet3 containes 2 mandatory columns
![image](https://user-images.githubusercontent.com/102654728/174078037-8a9e04e0-6bff-4af4-9a98-7fc4b05ea7e1.png)

There are few steps for arranging packing, which implemented in definitions
step 1 - "#load from excel" block of code. on this step we are reading excel file with ASINs and quantities, taking box dimensions from box_template string. preparing "qty_to_ship" DataFrame
step 2 - create_boxes_df_from_sku_df(qty_to_ship) - making box list and giving name for every box. getting pack_df DataFrame
step 3 - pack_goods_from_df_v3(pack_df, Pallet_W, Pallet_H, Pallet_D, Pallet_max_weight) - packing box list "pack_df" to the Pallet with dimensions W H D and max weight 
pack_goods_from_df_v3(pack_df, Pallet_W, Pallet_H, Pallet_D, Pallet_max_weight) returns 2 dataframes, one is box packlist, another one is pallet list
step 4 - make_excel_file(output[0], output[1]) - save packlists files, making and saving visualisation

![image](https://user-images.githubusercontent.com/102654728/174080598-d0e73f1f-db61-4469-ac76-4746f127c848.png)
