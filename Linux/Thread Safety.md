# Thread Safety
Thread safety is the avoidance of data races. Data races are where data is set to correct or incorrect values depending on the order in which threads access and modify the data.

When no sharing is intended, each thread is given a private copy of the data. When sharing is important, synchronisation is required to make sure the program behaves deterministically.

A procedure can be called thread-safe when it is logically correct when executed by several threads.

You can make an unsafe procedure thread-safe by adding locks and unlocks to the procedure.