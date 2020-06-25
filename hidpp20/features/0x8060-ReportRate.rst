************************
Report Rate (``0x8060``)
************************

Feature to change the device report rate

.. table:: Table 1 - Functions

    == ====================== =========================================================
    ID          Name                               Description
    == ====================== =========================================================
    0  ``GetReportRateList``  Retrieve the various report rates supported by the device
    1  ``GetReportRate``      Return the current report rate in ms  
    2  ``SetReportRate``      Set the report rate in ms
    == ====================== =========================================================


Functions
=========


``GetReportRateList``
~~~~~~~~~~~~~~~~~~~~~

    Retrieve the various report rates supported by the device.
    Standard report rates are 1, 2, 4 and 8ms.

Arguments
    - None

Returns   	 
     - [8bits] reportRateList
  											 
    +-----+-----+-----+-----+----+-----+-----+-----+
    | 7   | 6   | 5   | 4   | 3  | 2   | 1   | 0   |
    +=====+=====+=====+=====+====+=====+=====+=====+
    | 8ms | 7ms | 6ms | 5ms |4ms | 3ms | 2ms | 1ms |
    +-----+-----+-----+-----+----+-----+-----+-----+

    0 = rate not supported, 1  supported

Errors
    - None


``GetReportRate``
~~~~~~~~~~~~~~~~~

Arguments
    - None

Returns
    - [8bits] reportRate        The current report rate in ms.

Errors
    - None


``SetReportRate``
~~~~~~~~~~~~~~~~~

    This function can be called only in host mode
    
Parameters
    - [8bits] reportRate        The new report rate in ms     

Returns
    - None

Errors
     - InvalidArgument (2) Invalid reportRate, not in host mode

