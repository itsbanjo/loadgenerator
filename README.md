# loadgenerator
Based on the loadgenerator from Google's microservices-demo, except that it is using https protocol to generate load an expose route of the microservices-demo


To deploy in Openshift:  
oc create -f manifest/loadgenerator.yaml
oc set env deployment/external-loadgenerator FRONTEND_ADDR=route.for.your.microservices.demo

you should see 0% failure upon changing the FRONTEND_ADDR

```

 Name                                                          # reqs      # fails  |     Avg     Min     Max  Median  |   req/s failures/s
--------------------------------------------------------------------------------------------------------------------------------------------
 GET /                                                             17     0(0.00%)  |    1072     264    2239    1100  |    0.20    0.00
 GET /cart                                                         21     0(0.00%)  |     790     260    1427     640  |    0.00    0.00
 POST /cart                                                        29     0(0.00%)  |    1093     742    1769    1100  |    0.30    0.00
```
