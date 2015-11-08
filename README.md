codis go packages

IN: n-client(go WritingLoop) --(Server.reqCh)-->  1-dispatch  --(taskRunner.in)--> m-backend(writeloop)

OUT1: m-backend(readloop -[taskRunner.out]-> writeloop)  --(session.backQ)-->  n-client(WritingLoop)

OUT2: n-client(redisTunnel -[session.backQ]-> WritingLoop)

