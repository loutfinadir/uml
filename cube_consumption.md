# There are 2 ways to run INA queries
- Mode Sync
  - Used in most cases with no chunks
  - With the chunk processing of the segments, used in the scenario where we identify the presence of Lookup Or Restrict Formula, we delegate the generation of horizon dates to MDS, which has the capability to evaluate the formula.
  https://wiki.one.int.sap/wiki/pages/viewpage.action?pageId=3457445054
- Mode Async
  - Used only when the the planning model is universal model type with tuple (account, measure)
    - In this scenario, we are generating multiple INA queries based on each tuple of (account, measure).
    https://wiki.one.int.sap/wiki/display/~I051401/New+Model%3A+Support+of+Influencers+with+formulas
  - The segment chunk can also be utilized when working with the universal model and the tuple has a lookup or restrict
  formula 
# For the writeback
* https://wiki.one.int.sap/wiki/display/~I051401/Composer+Olap+Planning+Architecture#ComposerOlapPlanningArchitecture-PlanningWritebackperchunk
- The writeback use chunks to write back into planning
    - If segments existe we do chunk to:
        - Segments
        - Dates
    - if Not we do chunk to:
        - Dates
