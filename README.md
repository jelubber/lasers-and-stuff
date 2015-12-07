# lasers-and-stuff
ArcPy code to be used in ArcMap 10.3.1 when working with raster datasets, shp files, and data tables
#Run through the python window in arcpy from ArcMap 10.3.1
#add temperature regime fields to each mineral shp file

arcpy.AddField_management("Calcite","LTempC","Double",25,25)
arcpy.AddField_management("Calcite","HTempC","Double",25,25)

arcpy.AddField_management("Dickite_Pyrophyllite","LTempC","Double",25,25)
arcpy.AddField_management("Dickite_Pyrophyllite","HTempC","Double",25,25)

arcpy.AddField_management("Epidote","LTempC","Double",25,25)
arcpy.AddField_management("Epidote","HTempC","Double",25,25)

arcpy.AddField_management("Kaolinite_Dickite_Alunite","LTempC","Double",25,25)
arcpy.AddField_management("Kaolinite_Dickite_Alunite","HTempC","Double",25,25)

arcpy.AddField_management("Sericite_Muscovite_Chlorite","LTempC","Double",25,25)
arcpy.AddField_management("Sericite_Muscovite_Chlorite","HTempC","Double",25,25)

arcpy.AddField_management("Smectite","LTempC","Double",25,25)
arcpy.AddField_management("Smectite","HTempC","Double",25,25)

#Give each temperature regime field a corresponding temperature

arcpy.CalculateField_management("Calcite","LTempC",160)
arcpy.CalculateField_management("Calcite","HTempC",300)

arcpy.CalculateField_management("Dickite_Pyrophyllite","LTempC",200)
arcpy.CalculateField_management("Dickite_Pyrophyllite","HTempC",250)

arcpy.CalculateField_management("Epidote","LTempC",240)
arcpy.CalculateField_management("Epidote","HTempC",260)

arcpy.CalculateField_management("Kaolinite_Dickite_Alunite","LTempC",120)
arcpy.CalculateField_management("Kaolinite_Dickite_Alunite","HTempC",200)

arcpy.CalculateField_management("Sericite_Muscovite_Chlorite","LTempC",180)
arcpy.CalculateField_management("Sericite_Muscovite_Chlorite","HTempC",225)

arcpy.CalculateField_management("Smectite","LTempC",0)
arcpy.CalculateField_management("Smectite","HTempC",180)

#Calculating Geodesic area for each polygon in the mineral shpfiles
arcpy.AddGeometryAttributes_management("Calcite","AREA_GEODESIC","KILOMETERS","SQUARE_KILOMETERS")

arcpy.AddGeometryAttributes_management("Al_Sericite","AREA_GEODESIC","KILOMETERS","SQUARE_KILOMETERS")

arcpy.AddGeometryAttributes_management("Dickite_Pyrophyllite","AREA_GEODESIC","KILOMETERS","SQUARE_KILOMETERS")

arcpy.AddGeometryAttributes_management("Epidote","AREA_GEODESIC","KILOMETERS","SQUARE_KILOMETERS")

arcpy.AddGeometryAttributes_management("Kaolinite_Dickite_Alunite","AREA_GEODESIC","KILOMETERS","SQUARE_KILOMETERS")

arcpy.AddGeometryAttributes_management("Sericite_Muscovite_Chlorite","AREA_GEODESIC","KILOMETERS","SQUARE_KILOMETERS")

arcpy.AddGeometryAttributes_management("Smectite","AREA_GEODESIC","KILOMETERS","SQUARE_KILOMETERS")
 
