# idr0161-yayon-thymus

The RareCyte images will have a MapAnnotation "com.glencoesoftware.stitcher.minmax" after import. They can be deleted like that:

```
omero hql -q --style csv --ids-only "select m from MapAnnotation m where m.ns = 'com.glencoesoftware.stitcher.minmax'" | cut -d "," -f 2 | cut -d : -f 2 >> ids.txt
for i in `cat ids.txt`;do omero delete --force MapAnnotationI:$i ; done
```
