# GIPEDI-WEEK-7-Report
### Submitted by Gegerin Konsam
### ID FENGS173
- -----------------
### Interaction with Madam Sonal Gupta
I interacted with Madam on 28th June 2021. We discussed the problem at hand regarding the HLS synthesis using C. As i was stuck with the programming syntax and because those where due to the header files. We broke down the debugging to the following steps:
- Read what header files are.
- Find out synthesizeable Header files, is Math.h synthesizeable ?
- Take a working code and change the header files and see if they compile correctly.
- Trace back errors and debug why the codes are not working.
- Ask experts in the relevant domain for specific questions on sites like stackedit,stackio etc.

After this Ma'am aslo instructed that i make a trello dashboard where i could organise what i was supposed to do:
![Alt text](https://user-images.githubusercontent.com/86422829/124173995-71f38b00-dac9-11eb-9d0c-63b7af721fab.PNG)

Later on I joined a 2 day seminar/tutorial on 29th June 2021 called _"AI/ML Accelerator Tutorial: C-level Design & Verification Using HLS"_ hosted by Siemens Semiconductors.
from the seminar i leanred :
- System C and C++ are used to perform High Level Synthesis.
- Specific libraries are required to perform Synthesis of hardware components.
- Matchlib.h is one such library that we can use for syntnesis.
- Python with Custom Packages generating HDL is not used for synthesis as all it does it map the function to RTL.
- Developing our own C algorithm and optimizing it is the goal of HLS as the generated RTL will be optimised and it would speed up development cycles by around 30x.
- huge difference of code line comparing HLS and hand coded RTL. 

After that i wrote a small code to compute the exponent fucntion, it successfully compiled and the algorithm was tested and verified.

![Alt text](https://user-images.githubusercontent.com/86422829/124174016-78820280-dac9-11eb-98b3-ad0e63a46ec6.PNG)

# Performance Estimates

### Timing (ns): 
    * Summary: 
    +--------+-------+----------+------------+
    |  Clock | Target| Estimated| Uncertainty|
    +--------+-------+----------+------------+
    |ap_clk  |   4.00|     3.486|        0.50|
    +--------+-------+----------+------------+ <

#### Latency (clock cycles): 
    * Summary: 
    +-----+-----+-----+-----+---------+
    |  Latency  |  Interval | Pipeline|
    | min | max | min | max |   Type  |
    +-----+-----+-----+-----+---------+
    |   41|   41|   41|   41|   none  |
    +-----+-----+-----+-----+---------+
#### Detail: 
        * Instance: 
        N/A

        * Loop: 
        N/A




# Utilization Estimates

    * Summary: 
    +-----------------+---------+-------+--------+--------+
    |       Name      | BRAM_18K| DSP48E|   FF   |   LUT  |
    +-----------------+---------+-------+--------+--------+
    |DSP              |        -|      -|       -|       -|
    |Expression       |        -|      -|       -|       -|
    |FIFO             |        -|      -|       -|       -|
    |Instance         |        -|     26|    2322|    3447|
    |Memory           |        -|      -|       -|       -|
    |Multiplexer      |        -|      -|       -|     189|
    |Register         |        -|      -|     170|       -|
    +-----------------+---------+-------+--------+--------+
    |Total            |        0|     26|    2492|    3636|
    +-----------------+---------+-------+--------+--------+
    |Available        |      650|    600|  202800|  101400|
    +-----------------+---------+-------+--------+--------+
    |Utilization (%)  |        0|      4|       1|       3|
    +-----------------+---------+-------+--------+--------+
    *Detail: 
        *Instance: 
        +-------------------------+----------------------+---------+-------+------+------+
        |         Instance        |        Module        | BRAM_18K| DSP48E|  FF  |  LUT |
        +-------------------------+----------------------+---------+-------+------+------+
        |cpp_math_dexp_64ndEe_U3  |cpp_math_dexp_64ndEe  |        0|     26|  2094|  3211|
        |cpp_math_fpext_32cud_U2  |cpp_math_fpext_32cud  |        0|      0|   100|   139|
        |cpp_math_fptrunc_bkb_U1  |cpp_math_fptrunc_bkb  |        0|      0|   128|    97|
        +-------------------------+----------------------+---------+-------+------+------+
        |Total                    |                      |        0|     26|  2322|  3447|
        +-------------------------+----------------------+---------+-------+------+------+

          * DSP48: 
          N/A

        * Memory: 
        N/A

        * FIFO: 
        N/A

        * Expression: 
        N/A

        * Multiplexer: 
        +-----------+-----+-----------+-----+-----------+
        |    Name   | LUT | Input Size| Bits| Total Bits|
        +-----------+-----+-----------+-----+-----------+
        |ap_NS_fsm  |  189|         43|    1|         43|
        +-----------+-----+-----------+-----+-----------+
        |Total      |  189|         43|    1|         43|
        +-----------+-----+-----------+-----+-----------+

        * Register: 
        +--------------+----+----+-----+-----------+
        |     Name     | FF | LUT| Bits| Const Bits|
        +--------------+----+----+-----+-----------+
        |ap_CS_fsm     |  42|   0|   42|          0|
        |tmp_1_reg_37  |  64|   0|   64|          0|
        |tmp_reg_32    |  64|   0|   64|          0|
        +--------------+----+----+-----+-----------+
        |Total         | 170|   0|  170|          0|
        +--------------+----+----+-----+-----------+

# Interface

    * Summary: 
          +-----------+-----+-----+------------+--------------+--------------+
          | RTL Ports | Dir | Bits|  Protocol  | Source Object|    C Type    |
          +-----------+-----+-----+------------+--------------+--------------+
          |ap_clk     |  in |    1| ap_ctrl_hs |   cpp_math   | return value |
          |ap_rst     |  in |    1| ap_ctrl_hs |   cpp_math   | return value |
          |ap_start   |  in |    1| ap_ctrl_hs |   cpp_math   | return value |
          |ap_done    | out |    1| ap_ctrl_hs |   cpp_math   | return value |
          |ap_idle    | out |    1| ap_ctrl_hs |   cpp_math   | return value |
          |ap_ready   | out |    1| ap_ctrl_hs |   cpp_math   | return value |
          |ap_return  | out |   32| ap_ctrl_hs |   cpp_math   | return value |
          |x          |  in |   32|   ap_none  |       x      |    scalar    |
          +-----------+-----+-----+------------+--------------+--------------+

# Update on Water Melon plant:
The water melon has not grown much after it developed its two leaves. The leaves only seem to get bigger.

# Weekly activities

## helped clean up the garage.

![Alt text](https://user-images.githubusercontent.com/86422829/124177892-7a01f980-dace-11eb-8010-5901c241b564.jpeg)

## helped deliver plants to customer.

![Alt text](https://user-images.githubusercontent.com/86422829/124177881-766e7280-dace-11eb-8765-659926ba6e26.jpeg)
## taught my brother, mother and aunt how to use excel for record keeping.

# Task for next 3 days

* complete behaviorual simulation of exponential function.
* compute tanh using 3 different libraries and compare the resource utilizations 
* successfully verify C algorithm and the RTL verification for final report. 
