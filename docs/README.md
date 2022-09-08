# Headline

> An awesome project.



```abap
data: books type table of sbook.

try.
    cl_salv_table=>factory( exporting list_display   = if_salv_c_bool_sap=>false
                            importing r_salv_table   = data(salv)
                            changing  t_table        = books ).

    salv->get_columns( )->set_optimize( abap_true ).   "优化列宽
    salv->get_functions( )->set_all( ).
    salv->display( ).
  catch cx_salv_msg cx_salv_not_found.
endtry.
```

