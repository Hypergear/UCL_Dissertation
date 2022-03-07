# Gantt chart

## Estimated
```mermaid
gantt
    dateFormat  YYYY-MM-DD
    title       Zhiheng Jiang dissertation gantt chart
    
    section Research proposal
    Research question & Gantt chart : done, rp_rq, 2022-03-05
    Background & literature review : active, rp_bglr ,after rp_rq, 3d
    Research design   : rp_rd, after rp_bglr, 5d
    Write proposal : rp_wp, after rp_rd, 5d
    Warp up documents : rp_wu, after rp_wp, 1d
    Submit proposal     :milestone, 2022-03-24, 0d

    section Literature review
    Dataset research          : active, lr_dr, 2022-03-05,5d
    Development tools selection : lr_dts, after lr_dr, 3d
    Research relative work    :lr_rw, after lr_dts, 7d
    Background reading        :lr_br, after lr_rw, 14d

    section Coding analysis
    Familiar with tools : ca_ft, 2022-04-05, 3d
    Coding : ca_coding, after ca_ft, 21d
    Testing : ca_test, after ca_coding, 5d

    section Draft writing
    Introduction: dw_i, 2022-05-05,2d
    Method : dw_m, after dw_i, 7d
    Results : dw_res, after dw_m, 10d
    Discussion : dw_d, after dw_res, 2d
    Conclusion : dw_c, after dw_d, 2d
    Reference : dw_ref, after dw_c, 1d
    Appendix : dw_a, after dw_ref, 10d
    Warp up documents : : dw_wu, after dw_a, 2d
    Supervisor preview     :milestone, 2022-07-01, 0d

    section Report adjustment
    Adjustment : active,adj_adj, 2022-07-01,15d
    Reference & grammar checking : active, after adj_adj,5d


    section Submission
    Warp up documents: : active, 2022-07-21,5d
    Final submission : milestone, 2022-08-22

```
