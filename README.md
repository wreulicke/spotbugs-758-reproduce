

This project is to reproduce https://github.com/spotbugs/spotbugs/issues/758.

## Reproduction and stacktraces

```
$ ./gradle spotbugsMain
> Task :spotbugsMain
The following errors occurred during analysis:
  Error processing opcode checkcast @ 82 in io.findify.s3mock.S3Mock.$anonfun$start$2 : (Lio.findify.s3mock.S3Mock;Ljava.lang.String;)Lscala.Function1;
    java.lang.IllegalArgumentException: Unknown signature [Ljava/lang/Object; for number 4
      At edu.umd.cs.findbugs.OpcodeStack$Item.<init>(OpcodeStack.java:671)
      At edu.umd.cs.findbugs.OpcodeStack.sawOpcode(OpcodeStack.java:1725)
      At edu.umd.cs.findbugs.bcel.OpcodeStackDetector.afterOpcode(OpcodeStackDetector.java:83)
      At edu.umd.cs.findbugs.visitclass.DismantleBytecode.visit(DismantleBytecode.java:884)
      At edu.umd.cs.findbugs.detect.FieldItemSummary.visit(FieldItemSummary.java:130)
      At edu.umd.cs.findbugs.visitclass.BetterVisitor.visitCode(BetterVisitor.java:218)
      At edu.umd.cs.findbugs.visitclass.PreorderVisitor.visitCode(PreorderVisitor.java:243)
      At edu.umd.cs.findbugs.bcel.OpcodeStackDetector.visitCode(OpcodeStackDetector.java:65)
      At org.apache.bcel.classfile.Code.accept(Code.java:132)
      At edu.umd.cs.findbugs.visitclass.PreorderVisitor.doVisitMethod(PreorderVisitor.java:315)
      At edu.umd.cs.findbugs.visitclass.PreorderVisitor.visitJavaClass(PreorderVisitor.java:403)
      At org.apache.bcel.classfile.JavaClass.accept(JavaClass.java:213)
      At edu.umd.cs.findbugs.BytecodeScanningDetector.visitClassContext(BytecodeScanningDetector.java:38)
      At edu.umd.cs.findbugs.DetectorToDetector2Adapter.visitClass(DetectorToDetector2Adapter.java:76)
      At edu.umd.cs.findbugs.FindBugs2.analyzeApplication(FindBugs2.java:1080)
      At edu.umd.cs.findbugs.FindBugs2.execute(FindBugs2.java:281)
      At com.github.spotbugs.internal.spotbugs.SpotBugsExecuter.runSpotbugs(SpotBugsExecuter.java:23)
      At sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
      At sun.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)
      At sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
      At java.lang.reflect.Method.invoke(Method.java:498)
      At org.gradle.process.internal.worker.request.WorkerAction.run(WorkerAction.java:101)
      At org.gradle.process.internal.worker.request.WorkerAction.runThenStop(WorkerAction.java:84)
      At sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
      At sun.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)
      At sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
      At java.lang.reflect.Method.invoke(Method.java:498)
      At org.gradle.internal.dispatch.ReflectionDispatch.dispatch(ReflectionDispatch.java:35)
      At org.gradle.internal.dispatch.ReflectionDispatch.dispatch(ReflectionDispatch.java:24)
      At org.gradle.internal.remote.internal.hub.MessageHubBackedObjectConnection$DispatchWrapper.dispatch(MessageHubBackedObjectConnection.java:155)
      At org.gradle.internal.remote.internal.hub.MessageHubBackedObjectConnection$DispatchWrapper.dispatch(MessageHubBackedObjectConnection.java:137)
      At org.gradle.internal.remote.internal.hub.MessageHub$Handler.run(MessageHub.java:404)
      At org.gradle.internal.concurrent.ExecutorPolicy$CatchAndRecordFailures.onExecute(ExecutorPolicy.java:63)
      At org.gradle.internal.concurrent.ManagedExecutorImpl$1.run(ManagedExecutorImpl.java:46)
      At java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1149)
      At java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:624)
      At org.gradle.internal.concurrent.ThreadFactoryImpl$ManagedThreadRunnable.run(ThreadFactoryImpl.java:55)
      At java.lang.Thread.run(Thread.java:748)
  Error processing opcode checkcast @ 64 in io.findify.s3mock.S3Mock.$anonfun$start$3 : (Lio.findify.s3mock.S3Mock;Ljava.lang.String;)Lscala.Function1;
    java.lang.IllegalArgumentException: Unknown signature [Ljava/lang/Object; for number 3
      At edu.umd.cs.findbugs.OpcodeStack$Item.<init>(OpcodeStack.java:671)
      At edu.umd.cs.findbugs.OpcodeStack.sawOpcode(OpcodeStack.java:1725)
      At edu.umd.cs.findbugs.bcel.OpcodeStackDetector.afterOpcode(OpcodeStackDetector.java:83)
      At edu.umd.cs.findbugs.visitclass.DismantleBytecode.visit(DismantleBytecode.java:884)
      At edu.umd.cs.findbugs.detect.FieldItemSummary.visit(FieldItemSummary.java:130)
      At edu.umd.cs.findbugs.visitclass.BetterVisitor.visitCode(BetterVisitor.java:218)
      At edu.umd.cs.findbugs.visitclass.PreorderVisitor.visitCode(PreorderVisitor.java:243)
      At edu.umd.cs.findbugs.bcel.OpcodeStackDetector.visitCode(OpcodeStackDetector.java:65)
      At org.apache.bcel.classfile.Code.accept(Code.java:132)
      At edu.umd.cs.findbugs.visitclass.PreorderVisitor.doVisitMethod(PreorderVisitor.java:315)
      At edu.umd.cs.findbugs.visitclass.PreorderVisitor.visitJavaClass(PreorderVisitor.java:403)
      At org.apache.bcel.classfile.JavaClass.accept(JavaClass.java:213)
      At edu.umd.cs.findbugs.BytecodeScanningDetector.visitClassContext(BytecodeScanningDetector.java:38)
      At edu.umd.cs.findbugs.DetectorToDetector2Adapter.visitClass(DetectorToDetector2Adapter.java:76)
      At edu.umd.cs.findbugs.FindBugs2.analyzeApplication(FindBugs2.java:1080)
      At edu.umd.cs.findbugs.FindBugs2.execute(FindBugs2.java:281)
      At com.github.spotbugs.internal.spotbugs.SpotBugsExecuter.runSpotbugs(SpotBugsExecuter.java:23)
      At sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
      At sun.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)
      At sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
      At java.lang.reflect.Method.invoke(Method.java:498)
      At org.gradle.process.internal.worker.request.WorkerAction.run(WorkerAction.java:101)
      At org.gradle.process.internal.worker.request.WorkerAction.runThenStop(WorkerAction.java:84)
      At sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
      At sun.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)
      At sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
      At java.lang.reflect.Method.invoke(Method.java:498)
      At org.gradle.internal.dispatch.ReflectionDispatch.dispatch(ReflectionDispatch.java:35)
      At org.gradle.internal.dispatch.ReflectionDispatch.dispatch(ReflectionDispatch.java:24)
      At org.gradle.internal.remote.internal.hub.MessageHubBackedObjectConnection$DispatchWrapper.dispatch(MessageHubBackedObjectConnection.java:155)
      At org.gradle.internal.remote.internal.hub.MessageHubBackedObjectConnection$DispatchWrapper.dispatch(MessageHubBackedObjectConnection.java:137)
      At org.gradle.internal.remote.internal.hub.MessageHub$Handler.run(MessageHub.java:404)
      At org.gradle.internal.concurrent.ExecutorPolicy$CatchAndRecordFailures.onExecute(ExecutorPolicy.java:63)
      At org.gradle.internal.concurrent.ManagedExecutorImpl$1.run(ManagedExecutorImpl.java:46)
      At java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1149)
      At java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:624)
      At org.gradle.internal.concurrent.ThreadFactoryImpl$ManagedThreadRunnable.run(ThreadFactoryImpl.java:55)
      At java.lang.Thread.run(Thread.java:748)
  Error processing opcode checkcast @ 176 in io.findify.s3mock.S3Mock.$anonfun$start$5 : (Lio.findify.s3mock.S3Mock;Lakka.stream.ActorMaterializer;Ljava.lang.String;Lscala.collection.immutable.Map;Lakka.http.scaladsl.model.Uri$Path;)Lscala.Function1;
    java.lang.IllegalArgumentException: Unknown signature [Ljava/lang/Object; for number 7
      At edu.umd.cs.findbugs.OpcodeStack$Item.<init>(OpcodeStack.java:671)
      At edu.umd.cs.findbugs.OpcodeStack.sawOpcode(OpcodeStack.java:1725)
      At edu.umd.cs.findbugs.bcel.OpcodeStackDetector.afterOpcode(OpcodeStackDetector.java:83)
      At edu.umd.cs.findbugs.visitclass.DismantleBytecode.visit(DismantleBytecode.java:884)
      At edu.umd.cs.findbugs.detect.FieldItemSummary.visit(FieldItemSummary.java:130)
      At edu.umd.cs.findbugs.visitclass.BetterVisitor.visitCode(BetterVisitor.java:218)
      At edu.umd.cs.findbugs.visitclass.PreorderVisitor.visitCode(PreorderVisitor.java:243)
      At edu.umd.cs.findbugs.bcel.OpcodeStackDetector.visitCode(OpcodeStackDetector.java:65)
      At org.apache.bcel.classfile.Code.accept(Code.java:132)
      At edu.umd.cs.findbugs.visitclass.PreorderVisitor.doVisitMethod(PreorderVisitor.java:315)
      At edu.umd.cs.findbugs.visitclass.PreorderVisitor.visitJavaClass(PreorderVisitor.java:403)
      At org.apache.bcel.classfile.JavaClass.accept(JavaClass.java:213)
      At edu.umd.cs.findbugs.BytecodeScanningDetector.visitClassContext(BytecodeScanningDetector.java:38)
      At edu.umd.cs.findbugs.DetectorToDetector2Adapter.visitClass(DetectorToDetector2Adapter.java:76)
      At edu.umd.cs.findbugs.FindBugs2.analyzeApplication(FindBugs2.java:1080)
      At edu.umd.cs.findbugs.FindBugs2.execute(FindBugs2.java:281)
      At com.github.spotbugs.internal.spotbugs.SpotBugsExecuter.runSpotbugs(SpotBugsExecuter.java:23)
      At sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
      At sun.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)
      At sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
      At java.lang.reflect.Method.invoke(Method.java:498)
      At org.gradle.process.internal.worker.request.WorkerAction.run(WorkerAction.java:101)
      At org.gradle.process.internal.worker.request.WorkerAction.runThenStop(WorkerAction.java:84)
      At sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
      At sun.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)
      At sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
      At java.lang.reflect.Method.invoke(Method.java:498)
      At org.gradle.internal.dispatch.ReflectionDispatch.dispatch(ReflectionDispatch.java:35)
      At org.gradle.internal.dispatch.ReflectionDispatch.dispatch(ReflectionDispatch.java:24)
      At org.gradle.internal.remote.internal.hub.MessageHubBackedObjectConnection$DispatchWrapper.dispatch(MessageHubBackedObjectConnection.java:155)
      At org.gradle.internal.remote.internal.hub.MessageHubBackedObjectConnection$DispatchWrapper.dispatch(MessageHubBackedObjectConnection.java:137)
      At org.gradle.internal.remote.internal.hub.MessageHub$Handler.run(MessageHub.java:404)
      At org.gradle.internal.concurrent.ExecutorPolicy$CatchAndRecordFailures.onExecute(ExecutorPolicy.java:63)
      At org.gradle.internal.concurrent.ManagedExecutorImpl$1.run(ManagedExecutorImpl.java:46)
      At java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1149)
      At java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:624)
      At org.gradle.internal.concurrent.ThreadFactoryImpl$ManagedThreadRunnable.run(ThreadFactoryImpl.java:55)
      At java.lang.Thread.run(Thread.java:748)
  Error processing opcode checkcast @ 51 in io.findify.s3mock.S3Mock.$anonfun$start$7 : (Lio.findify.s3mock.S3Mock;Lakka.http.scaladsl.model.HttpRequest;)Lakka.http.scaladsl.marshalling.ToResponseMarshallable;
    java.lang.IllegalArgumentException: Unknown signature [Ljava/lang/Object; for number 3
      At edu.umd.cs.findbugs.OpcodeStack$Item.<init>(OpcodeStack.java:671)
      At edu.umd.cs.findbugs.OpcodeStack.sawOpcode(OpcodeStack.java:1725)
      At edu.umd.cs.findbugs.bcel.OpcodeStackDetector.afterOpcode(OpcodeStackDetector.java:83)
      At edu.umd.cs.findbugs.visitclass.DismantleBytecode.visit(DismantleBytecode.java:884)
      At edu.umd.cs.findbugs.detect.FieldItemSummary.visit(FieldItemSummary.java:130)
      At edu.umd.cs.findbugs.visitclass.BetterVisitor.visitCode(BetterVisitor.java:218)
      At edu.umd.cs.findbugs.visitclass.PreorderVisitor.visitCode(PreorderVisitor.java:243)
      At edu.umd.cs.findbugs.bcel.OpcodeStackDetector.visitCode(OpcodeStackDetector.java:65)
      At org.apache.bcel.classfile.Code.accept(Code.java:132)
      At edu.umd.cs.findbugs.visitclass.PreorderVisitor.doVisitMethod(PreorderVisitor.java:315)
      At edu.umd.cs.findbugs.visitclass.PreorderVisitor.visitJavaClass(PreorderVisitor.java:403)
      At org.apache.bcel.classfile.JavaClass.accept(JavaClass.java:213)
      At edu.umd.cs.findbugs.BytecodeScanningDetector.visitClassContext(BytecodeScanningDetector.java:38)
      At edu.umd.cs.findbugs.DetectorToDetector2Adapter.visitClass(DetectorToDetector2Adapter.java:76)
      At edu.umd.cs.findbugs.FindBugs2.analyzeApplication(FindBugs2.java:1080)
      At edu.umd.cs.findbugs.FindBugs2.execute(FindBugs2.java:281)
      At com.github.spotbugs.internal.spotbugs.SpotBugsExecuter.runSpotbugs(SpotBugsExecuter.java:23)
      At sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
      At sun.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)
      At sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
      At java.lang.reflect.Method.invoke(Method.java:498)
      At org.gradle.process.internal.worker.request.WorkerAction.run(WorkerAction.java:101)
      At org.gradle.process.internal.worker.request.WorkerAction.runThenStop(WorkerAction.java:84)
      At sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
      At sun.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)
      At sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
      At java.lang.reflect.Method.invoke(Method.java:498)
      At org.gradle.internal.dispatch.ReflectionDispatch.dispatch(ReflectionDispatch.java:35)
      At org.gradle.internal.dispatch.ReflectionDispatch.dispatch(ReflectionDispatch.java:24)
      At org.gradle.internal.remote.internal.hub.MessageHubBackedObjectConnection$DispatchWrapper.dispatch(MessageHubBackedObjectConnection.java:155)
      At org.gradle.internal.remote.internal.hub.MessageHubBackedObjectConnection$DispatchWrapper.dispatch(MessageHubBackedObjectConnection.java:137)
      At org.gradle.internal.remote.internal.hub.MessageHub$Handler.run(MessageHub.java:404)
      At org.gradle.internal.concurrent.ExecutorPolicy$CatchAndRecordFailures.onExecute(ExecutorPolicy.java:63)
      At org.gradle.internal.concurrent.ManagedExecutorImpl$1.run(ManagedExecutorImpl.java:46)
      At java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1149)
      At java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:624)
      At org.gradle.internal.concurrent.ThreadFactoryImpl$ManagedThreadRunnable.run(ThreadFactoryImpl.java:55)
      At java.lang.Thread.run(Thread.java:748)
  Error processing opcode checkcast @ 82 in io.findify.s3mock.S3Mock.$anonfun$start$2 : (Lio.findify.s3mock.S3Mock;Ljava.lang.String;)Lscala.Function1;
    java.lang.IllegalArgumentException: Unknown signature [Ljava/lang/Object; for number 4
      At edu.umd.cs.findbugs.OpcodeStack$Item.<init>(OpcodeStack.java:671)
      At edu.umd.cs.findbugs.OpcodeStack.sawOpcode(OpcodeStack.java:1725)
      At edu.umd.cs.findbugs.bcel.OpcodeStackDetector.afterOpcode(OpcodeStackDetector.java:83)
      At edu.umd.cs.findbugs.visitclass.DismantleBytecode.visit(DismantleBytecode.java:884)
      At edu.umd.cs.findbugs.detect.FindNoSideEffectMethods.visit(FindNoSideEffectMethods.java:492)
      At edu.umd.cs.findbugs.visitclass.BetterVisitor.visitCode(BetterVisitor.java:218)
      At edu.umd.cs.findbugs.visitclass.PreorderVisitor.visitCode(PreorderVisitor.java:243)
      At edu.umd.cs.findbugs.bcel.OpcodeStackDetector.visitCode(OpcodeStackDetector.java:65)
      At org.apache.bcel.classfile.Code.accept(Code.java:132)
      At edu.umd.cs.findbugs.visitclass.PreorderVisitor.doVisitMethod(PreorderVisitor.java:315)
      At edu.umd.cs.findbugs.visitclass.PreorderVisitor.visitJavaClass(PreorderVisitor.java:403)
      At org.apache.bcel.classfile.JavaClass.accept(JavaClass.java:213)
      At edu.umd.cs.findbugs.BytecodeScanningDetector.visitClassContext(BytecodeScanningDetector.java:38)
      At edu.umd.cs.findbugs.DetectorToDetector2Adapter.visitClass(DetectorToDetector2Adapter.java:76)
      At edu.umd.cs.findbugs.FindBugs2.analyzeApplication(FindBugs2.java:1080)
      At edu.umd.cs.findbugs.FindBugs2.execute(FindBugs2.java:281)
      At com.github.spotbugs.internal.spotbugs.SpotBugsExecuter.runSpotbugs(SpotBugsExecuter.java:23)
      At sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
      At sun.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)
      At sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
      At java.lang.reflect.Method.invoke(Method.java:498)
      At org.gradle.process.internal.worker.request.WorkerAction.run(WorkerAction.java:101)
      At org.gradle.process.internal.worker.request.WorkerAction.runThenStop(WorkerAction.java:84)
      At sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
      At sun.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)
      At sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
      At java.lang.reflect.Method.invoke(Method.java:498)
      At org.gradle.internal.dispatch.ReflectionDispatch.dispatch(ReflectionDispatch.java:35)
      At org.gradle.internal.dispatch.ReflectionDispatch.dispatch(ReflectionDispatch.java:24)
      At org.gradle.internal.remote.internal.hub.MessageHubBackedObjectConnection$DispatchWrapper.dispatch(MessageHubBackedObjectConnection.java:155)
      At org.gradle.internal.remote.internal.hub.MessageHubBackedObjectConnection$DispatchWrapper.dispatch(MessageHubBackedObjectConnection.java:137)
      At org.gradle.internal.remote.internal.hub.MessageHub$Handler.run(MessageHub.java:404)
      At org.gradle.internal.concurrent.ExecutorPolicy$CatchAndRecordFailures.onExecute(ExecutorPolicy.java:63)
      At org.gradle.internal.concurrent.ManagedExecutorImpl$1.run(ManagedExecutorImpl.java:46)
      At java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1149)
      At java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:624)
      At org.gradle.internal.concurrent.ThreadFactoryImpl$ManagedThreadRunnable.run(ThreadFactoryImpl.java:55)
      At java.lang.Thread.run(Thread.java:748)
  Error processing opcode checkcast @ 64 in io.findify.s3mock.S3Mock.$anonfun$start$3 : (Lio.findify.s3mock.S3Mock;Ljava.lang.String;)Lscala.Function1;
    java.lang.IllegalArgumentException: Unknown signature [Ljava/lang/Object; for number 3
      At edu.umd.cs.findbugs.OpcodeStack$Item.<init>(OpcodeStack.java:671)
      At edu.umd.cs.findbugs.OpcodeStack.sawOpcode(OpcodeStack.java:1725)
      At edu.umd.cs.findbugs.bcel.OpcodeStackDetector.afterOpcode(OpcodeStackDetector.java:83)
      At edu.umd.cs.findbugs.visitclass.DismantleBytecode.visit(DismantleBytecode.java:884)
      At edu.umd.cs.findbugs.detect.FindNoSideEffectMethods.visit(FindNoSideEffectMethods.java:492)
      At edu.umd.cs.findbugs.visitclass.BetterVisitor.visitCode(BetterVisitor.java:218)
      At edu.umd.cs.findbugs.visitclass.PreorderVisitor.visitCode(PreorderVisitor.java:243)
      At edu.umd.cs.findbugs.bcel.OpcodeStackDetector.visitCode(OpcodeStackDetector.java:65)
      At org.apache.bcel.classfile.Code.accept(Code.java:132)
      At edu.umd.cs.findbugs.visitclass.PreorderVisitor.doVisitMethod(PreorderVisitor.java:315)
      At edu.umd.cs.findbugs.visitclass.PreorderVisitor.visitJavaClass(PreorderVisitor.java:403)
      At org.apache.bcel.classfile.JavaClass.accept(JavaClass.java:213)
      At edu.umd.cs.findbugs.BytecodeScanningDetector.visitClassContext(BytecodeScanningDetector.java:38)
      At edu.umd.cs.findbugs.DetectorToDetector2Adapter.visitClass(DetectorToDetector2Adapter.java:76)
      At edu.umd.cs.findbugs.FindBugs2.analyzeApplication(FindBugs2.java:1080)
      At edu.umd.cs.findbugs.FindBugs2.execute(FindBugs2.java:281)
      At com.github.spotbugs.internal.spotbugs.SpotBugsExecuter.runSpotbugs(SpotBugsExecuter.java:23)
      At sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
      At sun.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)
      At sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
      At java.lang.reflect.Method.invoke(Method.java:498)
      At org.gradle.process.internal.worker.request.WorkerAction.run(WorkerAction.java:101)
      At org.gradle.process.internal.worker.request.WorkerAction.runThenStop(WorkerAction.java:84)
      At sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
      At sun.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)
      At sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
      At java.lang.reflect.Method.invoke(Method.java:498)
      At org.gradle.internal.dispatch.ReflectionDispatch.dispatch(ReflectionDispatch.java:35)
      At org.gradle.internal.dispatch.ReflectionDispatch.dispatch(ReflectionDispatch.java:24)
      At org.gradle.internal.remote.internal.hub.MessageHubBackedObjectConnection$DispatchWrapper.dispatch(MessageHubBackedObjectConnection.java:155)
      At org.gradle.internal.remote.internal.hub.MessageHubBackedObjectConnection$DispatchWrapper.dispatch(MessageHubBackedObjectConnection.java:137)
      At org.gradle.internal.remote.internal.hub.MessageHub$Handler.run(MessageHub.java:404)
      At org.gradle.internal.concurrent.ExecutorPolicy$CatchAndRecordFailures.onExecute(ExecutorPolicy.java:63)
      At org.gradle.internal.concurrent.ManagedExecutorImpl$1.run(ManagedExecutorImpl.java:46)
      At java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1149)
      At java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:624)
      At org.gradle.internal.concurrent.ThreadFactoryImpl$ManagedThreadRunnable.run(ThreadFactoryImpl.java:55)
      At java.lang.Thread.run(Thread.java:748)
  Error processing opcode checkcast @ 176 in io.findify.s3mock.S3Mock.$anonfun$start$5 : (Lio.findify.s3mock.S3Mock;Lakka.stream.ActorMaterializer;Ljava.lang.String;Lscala.collection.immutable.Map;Lakka.http.scaladsl.model.Uri$Path;)Lscala.Function1;
    java.lang.IllegalArgumentException: Unknown signature [Ljava/lang/Object; for number 7
      At edu.umd.cs.findbugs.OpcodeStack$Item.<init>(OpcodeStack.java:671)
      At edu.umd.cs.findbugs.OpcodeStack.sawOpcode(OpcodeStack.java:1725)
      At edu.umd.cs.findbugs.bcel.OpcodeStackDetector.afterOpcode(OpcodeStackDetector.java:83)
      At edu.umd.cs.findbugs.visitclass.DismantleBytecode.visit(DismantleBytecode.java:884)
      At edu.umd.cs.findbugs.detect.FindNoSideEffectMethods.visit(FindNoSideEffectMethods.java:492)
      At edu.umd.cs.findbugs.visitclass.BetterVisitor.visitCode(BetterVisitor.java:218)
      At edu.umd.cs.findbugs.visitclass.PreorderVisitor.visitCode(PreorderVisitor.java:243)
      At edu.umd.cs.findbugs.bcel.OpcodeStackDetector.visitCode(OpcodeStackDetector.java:65)
      At org.apache.bcel.classfile.Code.accept(Code.java:132)
      At edu.umd.cs.findbugs.visitclass.PreorderVisitor.doVisitMethod(PreorderVisitor.java:315)
      At edu.umd.cs.findbugs.visitclass.PreorderVisitor.visitJavaClass(PreorderVisitor.java:403)
      At org.apache.bcel.classfile.JavaClass.accept(JavaClass.java:213)
      At edu.umd.cs.findbugs.BytecodeScanningDetector.visitClassContext(BytecodeScanningDetector.java:38)
      At edu.umd.cs.findbugs.DetectorToDetector2Adapter.visitClass(DetectorToDetector2Adapter.java:76)
      At edu.umd.cs.findbugs.FindBugs2.analyzeApplication(FindBugs2.java:1080)
      At edu.umd.cs.findbugs.FindBugs2.execute(FindBugs2.java:281)
      At com.github.spotbugs.internal.spotbugs.SpotBugsExecuter.runSpotbugs(SpotBugsExecuter.java:23)
      At sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
      At sun.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)
      At sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
      At java.lang.reflect.Method.invoke(Method.java:498)
      At org.gradle.process.internal.worker.request.WorkerAction.run(WorkerAction.java:101)
      At org.gradle.process.internal.worker.request.WorkerAction.runThenStop(WorkerAction.java:84)
      At sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
      At sun.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)
      At sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
      At java.lang.reflect.Method.invoke(Method.java:498)
      At org.gradle.internal.dispatch.ReflectionDispatch.dispatch(ReflectionDispatch.java:35)
      At org.gradle.internal.dispatch.ReflectionDispatch.dispatch(ReflectionDispatch.java:24)
      At org.gradle.internal.remote.internal.hub.MessageHubBackedObjectConnection$DispatchWrapper.dispatch(MessageHubBackedObjectConnection.java:155)
      At org.gradle.internal.remote.internal.hub.MessageHubBackedObjectConnection$DispatchWrapper.dispatch(MessageHubBackedObjectConnection.java:137)
      At org.gradle.internal.remote.internal.hub.MessageHub$Handler.run(MessageHub.java:404)
      At org.gradle.internal.concurrent.ExecutorPolicy$CatchAndRecordFailures.onExecute(ExecutorPolicy.java:63)
      At org.gradle.internal.concurrent.ManagedExecutorImpl$1.run(ManagedExecutorImpl.java:46)
      At java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1149)
      At java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:624)
      At org.gradle.internal.concurrent.ThreadFactoryImpl$ManagedThreadRunnable.run(ThreadFactoryImpl.java:55)
      At java.lang.Thread.run(Thread.java:748)
  Error processing opcode checkcast @ 51 in io.findify.s3mock.S3Mock.$anonfun$start$7 : (Lio.findify.s3mock.S3Mock;Lakka.http.scaladsl.model.HttpRequest;)Lakka.http.scaladsl.marshalling.ToResponseMarshallable;
    java.lang.IllegalArgumentException: Unknown signature [Ljava/lang/Object; for number 3
      At edu.umd.cs.findbugs.OpcodeStack$Item.<init>(OpcodeStack.java:671)
      At edu.umd.cs.findbugs.OpcodeStack.sawOpcode(OpcodeStack.java:1725)
      At edu.umd.cs.findbugs.bcel.OpcodeStackDetector.afterOpcode(OpcodeStackDetector.java:83)
      At edu.umd.cs.findbugs.visitclass.DismantleBytecode.visit(DismantleBytecode.java:884)
      At edu.umd.cs.findbugs.detect.FindNoSideEffectMethods.visit(FindNoSideEffectMethods.java:492)
      At edu.umd.cs.findbugs.visitclass.BetterVisitor.visitCode(BetterVisitor.java:218)
      At edu.umd.cs.findbugs.visitclass.PreorderVisitor.visitCode(PreorderVisitor.java:243)
      At edu.umd.cs.findbugs.bcel.OpcodeStackDetector.visitCode(OpcodeStackDetector.java:65)
      At org.apache.bcel.classfile.Code.accept(Code.java:132)
      At edu.umd.cs.findbugs.visitclass.PreorderVisitor.doVisitMethod(PreorderVisitor.java:315)
      At edu.umd.cs.findbugs.visitclass.PreorderVisitor.visitJavaClass(PreorderVisitor.java:403)
      At org.apache.bcel.classfile.JavaClass.accept(JavaClass.java:213)
      At edu.umd.cs.findbugs.BytecodeScanningDetector.visitClassContext(BytecodeScanningDetector.java:38)
      At edu.umd.cs.findbugs.DetectorToDetector2Adapter.visitClass(DetectorToDetector2Adapter.java:76)
      At edu.umd.cs.findbugs.FindBugs2.analyzeApplication(FindBugs2.java:1080)
      At edu.umd.cs.findbugs.FindBugs2.execute(FindBugs2.java:281)
      At com.github.spotbugs.internal.spotbugs.SpotBugsExecuter.runSpotbugs(SpotBugsExecuter.java:23)
      At sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
      At sun.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)
      At sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
      At java.lang.reflect.Method.invoke(Method.java:498)
      At org.gradle.process.internal.worker.request.WorkerAction.run(WorkerAction.java:101)
      At org.gradle.process.internal.worker.request.WorkerAction.runThenStop(WorkerAction.java:84)
      At sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
      At sun.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)
      At sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
      At java.lang.reflect.Method.invoke(Method.java:498)
      At org.gradle.internal.dispatch.ReflectionDispatch.dispatch(ReflectionDispatch.java:35)
      At org.gradle.internal.dispatch.ReflectionDispatch.dispatch(ReflectionDispatch.java:24)
      At org.gradle.internal.remote.internal.hub.MessageHubBackedObjectConnection$DispatchWrapper.dispatch(MessageHubBackedObjectConnection.java:155)
      At org.gradle.internal.remote.internal.hub.MessageHubBackedObjectConnection$DispatchWrapper.dispatch(MessageHubBackedObjectConnection.java:137)
      At org.gradle.internal.remote.internal.hub.MessageHub$Handler.run(MessageHub.java:404)
      At org.gradle.internal.concurrent.ExecutorPolicy$CatchAndRecordFailures.onExecute(ExecutorPolicy.java:63)
      At org.gradle.internal.concurrent.ManagedExecutorImpl$1.run(ManagedExecutorImpl.java:46)
      At java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1149)
      At java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:624)
      At org.gradle.internal.concurrent.ThreadFactoryImpl$ManagedThreadRunnable.run(ThreadFactoryImpl.java:55)
      At java.lang.Thread.run(Thread.java:748)
  Error processing opcode checkcast @ 82 in io.findify.s3mock.S3Mock.$anonfun$start$2 : (Lio.findify.s3mock.S3Mock;Ljava.lang.String;)Lscala.Function1;
    java.lang.IllegalArgumentException: Unknown signature [Ljava/lang/Object; for number 4
      At edu.umd.cs.findbugs.OpcodeStack$Item.<init>(OpcodeStack.java:671)
      At edu.umd.cs.findbugs.OpcodeStack.sawOpcode(OpcodeStack.java:1725)
      At edu.umd.cs.findbugs.bcel.OpcodeStackDetector.afterOpcode(OpcodeStackDetector.java:83)
      At edu.umd.cs.findbugs.visitclass.DismantleBytecode.visit(DismantleBytecode.java:884)
      At edu.umd.cs.findbugs.visitclass.BetterVisitor.visitCode(BetterVisitor.java:218)
      At edu.umd.cs.findbugs.visitclass.PreorderVisitor.visitCode(PreorderVisitor.java:243)
      At edu.umd.cs.findbugs.bcel.OpcodeStackDetector.visitCode(OpcodeStackDetector.java:65)
      At org.apache.bcel.classfile.Code.accept(Code.java:132)
      At edu.umd.cs.findbugs.visitclass.PreorderVisitor.doVisitMethod(PreorderVisitor.java:315)
      At edu.umd.cs.findbugs.visitclass.PreorderVisitor.visitJavaClass(PreorderVisitor.java:403)
      At org.apache.bcel.classfile.JavaClass.accept(JavaClass.java:213)
      At edu.umd.cs.findbugs.BytecodeScanningDetector.visitClassContext(BytecodeScanningDetector.java:38)
      At edu.umd.cs.findbugs.DetectorToDetector2Adapter.visitClass(DetectorToDetector2Adapter.java:76)
      At edu.umd.cs.findbugs.FindBugs2.analyzeApplication(FindBugs2.java:1080)
      At edu.umd.cs.findbugs.FindBugs2.execute(FindBugs2.java:281)
      At com.github.spotbugs.internal.spotbugs.SpotBugsExecuter.runSpotbugs(SpotBugsExecuter.java:23)
      At sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
      At sun.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)
      At sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
      At java.lang.reflect.Method.invoke(Method.java:498)
      At org.gradle.process.internal.worker.request.WorkerAction.run(WorkerAction.java:101)
      At org.gradle.process.internal.worker.request.WorkerAction.runThenStop(WorkerAction.java:84)
      At sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
      At sun.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)
      At sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
      At java.lang.reflect.Method.invoke(Method.java:498)
      At org.gradle.internal.dispatch.ReflectionDispatch.dispatch(ReflectionDispatch.java:35)
      At org.gradle.internal.dispatch.ReflectionDispatch.dispatch(ReflectionDispatch.java:24)
      At org.gradle.internal.remote.internal.hub.MessageHubBackedObjectConnection$DispatchWrapper.dispatch(MessageHubBackedObjectConnection.java:155)
      At org.gradle.internal.remote.internal.hub.MessageHubBackedObjectConnection$DispatchWrapper.dispatch(MessageHubBackedObjectConnection.java:137)
      At org.gradle.internal.remote.internal.hub.MessageHub$Handler.run(MessageHub.java:404)
      At org.gradle.internal.concurrent.ExecutorPolicy$CatchAndRecordFailures.onExecute(ExecutorPolicy.java:63)
      At org.gradle.internal.concurrent.ManagedExecutorImpl$1.run(ManagedExecutorImpl.java:46)
      At java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1149)
      At java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:624)
      At org.gradle.internal.concurrent.ThreadFactoryImpl$ManagedThreadRunnable.run(ThreadFactoryImpl.java:55)
      At java.lang.Thread.run(Thread.java:748)
  Error processing opcode checkcast @ 64 in io.findify.s3mock.S3Mock.$anonfun$start$3 : (Lio.findify.s3mock.S3Mock;Ljava.lang.String;)Lscala.Function1;
    java.lang.IllegalArgumentException: Unknown signature [Ljava/lang/Object; for number 3
      At edu.umd.cs.findbugs.OpcodeStack$Item.<init>(OpcodeStack.java:671)
      At edu.umd.cs.findbugs.OpcodeStack.sawOpcode(OpcodeStack.java:1725)
      At edu.umd.cs.findbugs.bcel.OpcodeStackDetector.afterOpcode(OpcodeStackDetector.java:83)
      At edu.umd.cs.findbugs.visitclass.DismantleBytecode.visit(DismantleBytecode.java:884)
      At edu.umd.cs.findbugs.visitclass.BetterVisitor.visitCode(BetterVisitor.java:218)
      At edu.umd.cs.findbugs.visitclass.PreorderVisitor.visitCode(PreorderVisitor.java:243)
      At edu.umd.cs.findbugs.bcel.OpcodeStackDetector.visitCode(OpcodeStackDetector.java:65)
      At org.apache.bcel.classfile.Code.accept(Code.java:132)
      At edu.umd.cs.findbugs.visitclass.PreorderVisitor.doVisitMethod(PreorderVisitor.java:315)
      At edu.umd.cs.findbugs.visitclass.PreorderVisitor.visitJavaClass(PreorderVisitor.java:403)
      At org.apache.bcel.classfile.JavaClass.accept(JavaClass.java:213)
      At edu.umd.cs.findbugs.BytecodeScanningDetector.visitClassContext(BytecodeScanningDetector.java:38)
      At edu.umd.cs.findbugs.DetectorToDetector2Adapter.visitClass(DetectorToDetector2Adapter.java:76)
      At edu.umd.cs.findbugs.FindBugs2.analyzeApplication(FindBugs2.java:1080)
      At edu.umd.cs.findbugs.FindBugs2.execute(FindBugs2.java:281)
      At com.github.spotbugs.internal.spotbugs.SpotBugsExecuter.runSpotbugs(SpotBugsExecuter.java:23)
      At sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
      At sun.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)
      At sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
      At java.lang.reflect.Method.invoke(Method.java:498)
      At org.gradle.process.internal.worker.request.WorkerAction.run(WorkerAction.java:101)
      At org.gradle.process.internal.worker.request.WorkerAction.runThenStop(WorkerAction.java:84)
      At sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
      At sun.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)
      At sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
      At java.lang.reflect.Method.invoke(Method.java:498)
      At org.gradle.internal.dispatch.ReflectionDispatch.dispatch(ReflectionDispatch.java:35)
      At org.gradle.internal.dispatch.ReflectionDispatch.dispatch(ReflectionDispatch.java:24)
      At org.gradle.internal.remote.internal.hub.MessageHubBackedObjectConnection$DispatchWrapper.dispatch(MessageHubBackedObjectConnection.java:155)
      At org.gradle.internal.remote.internal.hub.MessageHubBackedObjectConnection$DispatchWrapper.dispatch(MessageHubBackedObjectConnection.java:137)
      At org.gradle.internal.remote.internal.hub.MessageHub$Handler.run(MessageHub.java:404)
      At org.gradle.internal.concurrent.ExecutorPolicy$CatchAndRecordFailures.onExecute(ExecutorPolicy.java:63)
      At org.gradle.internal.concurrent.ManagedExecutorImpl$1.run(ManagedExecutorImpl.java:46)
      At java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1149)
      At java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:624)
      At org.gradle.internal.concurrent.ThreadFactoryImpl$ManagedThreadRunnable.run(ThreadFactoryImpl.java:55)
      At java.lang.Thread.run(Thread.java:748)
  Error processing opcode checkcast @ 176 in io.findify.s3mock.S3Mock.$anonfun$start$5 : (Lio.findify.s3mock.S3Mock;Lakka.stream.ActorMaterializer;Ljava.lang.String;Lscala.collection.immutable.Map;Lakka.http.scaladsl.model.Uri$Path;)Lscala.Function1;
    java.lang.IllegalArgumentException: Unknown signature [Ljava/lang/Object; for number 7
      At edu.umd.cs.findbugs.OpcodeStack$Item.<init>(OpcodeStack.java:671)
      At edu.umd.cs.findbugs.OpcodeStack.sawOpcode(OpcodeStack.java:1725)
      At edu.umd.cs.findbugs.bcel.OpcodeStackDetector.afterOpcode(OpcodeStackDetector.java:83)
      At edu.umd.cs.findbugs.visitclass.DismantleBytecode.visit(DismantleBytecode.java:884)
      At edu.umd.cs.findbugs.visitclass.BetterVisitor.visitCode(BetterVisitor.java:218)
      At edu.umd.cs.findbugs.visitclass.PreorderVisitor.visitCode(PreorderVisitor.java:243)
      At edu.umd.cs.findbugs.bcel.OpcodeStackDetector.visitCode(OpcodeStackDetector.java:65)
      At org.apache.bcel.classfile.Code.accept(Code.java:132)
      At edu.umd.cs.findbugs.visitclass.PreorderVisitor.doVisitMethod(PreorderVisitor.java:315)
      At edu.umd.cs.findbugs.visitclass.PreorderVisitor.visitJavaClass(PreorderVisitor.java:403)
      At org.apache.bcel.classfile.JavaClass.accept(JavaClass.java:213)
      At edu.umd.cs.findbugs.BytecodeScanningDetector.visitClassContext(BytecodeScanningDetector.java:38)
      At edu.umd.cs.findbugs.DetectorToDetector2Adapter.visitClass(DetectorToDetector2Adapter.java:76)
      At edu.umd.cs.findbugs.FindBugs2.analyzeApplication(FindBugs2.java:1080)
      At edu.umd.cs.findbugs.FindBugs2.execute(FindBugs2.java:281)
      At com.github.spotbugs.internal.spotbugs.SpotBugsExecuter.runSpotbugs(SpotBugsExecuter.java:23)
      At sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
      At sun.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)
      At sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
      At java.lang.reflect.Method.invoke(Method.java:498)
      At org.gradle.process.internal.worker.request.WorkerAction.run(WorkerAction.java:101)
      At org.gradle.process.internal.worker.request.WorkerAction.runThenStop(WorkerAction.java:84)
      At sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
      At sun.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)
      At sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
      At java.lang.reflect.Method.invoke(Method.java:498)
      At org.gradle.internal.dispatch.ReflectionDispatch.dispatch(ReflectionDispatch.java:35)
      At org.gradle.internal.dispatch.ReflectionDispatch.dispatch(ReflectionDispatch.java:24)
      At org.gradle.internal.remote.internal.hub.MessageHubBackedObjectConnection$DispatchWrapper.dispatch(MessageHubBackedObjectConnection.java:155)
      At org.gradle.internal.remote.internal.hub.MessageHubBackedObjectConnection$DispatchWrapper.dispatch(MessageHubBackedObjectConnection.java:137)
      At org.gradle.internal.remote.internal.hub.MessageHub$Handler.run(MessageHub.java:404)
      At org.gradle.internal.concurrent.ExecutorPolicy$CatchAndRecordFailures.onExecute(ExecutorPolicy.java:63)
      At org.gradle.internal.concurrent.ManagedExecutorImpl$1.run(ManagedExecutorImpl.java:46)
      At java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1149)
      At java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:624)
      At org.gradle.internal.concurrent.ThreadFactoryImpl$ManagedThreadRunnable.run(ThreadFactoryImpl.java:55)
      At java.lang.Thread.run(Thread.java:748)
```

## Show Code Attribute

```
$ javap -p -v io/findify/s3mock/S3Mock.class > memo
$ cat memo

Classfile /Users/saito.masaya/work/io/findify/s3mock/S3Mock.class
  Last modified 2017/06/19; size 16833 bytes
  MD5 checksum 36ba222bfbf5871334a819f5be622889
  Compiled from "S3Mock.scala"
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
  public static final scala.Function1 $anonfun$start$5(io.findify.s3mock.S3Mock, akka.stream.ActorMaterializer, java.lang.String, scala.collection.immutable.Map, akka.http.scaladsl.model.Uri$Path);
    descriptor: (Lio/findify/s3mock/S3Mock;Lakka/stream/ActorMaterializer;Ljava/lang/String;Lscala/collection/immutable/Map;Lakka/http/scaladsl/model/Uri$Path;)Lscala/Function1;
    flags: ACC_PUBLIC, ACC_STATIC, ACC_FINAL, ACC_SYNTHETIC
    Code:
      stack=9, locals=5, args_size=5
         0: getstatic     #145                // Field akka/http/scaladsl/server/Directives$.MODULE$:Lakka/http/scaladsl/server/Directives$;
         3: getstatic     #356                // Field scala/Predef$.MODULE$:Lscala/Predef$;
         6: bipush        7
         8: anewarray     #196                // class scala/Function1
        11: dup
        12: iconst_0
        13: new           #392                // class io/findify/s3mock/route/GetObject
        16: dup
        17: aload_0
        18: invokevirtual #206                // Method p:()Lio/findify/s3mock/provider/Provider;
        21: invokespecial #393                // Method io/findify/s3mock/route/GetObject."<init>":(Lio/findify/s3mock/provider/Provider;)V
        24: aload_2
        25: aload         4
        27: invokevirtual #397                // Method akka/http/scaladsl/model/Uri$Path.toString:()Ljava/lang/String;
        30: aload_3
        31: invokevirtual #400                // Method io/findify/s3mock/route/GetObject.route:(Ljava/lang/String;Ljava/lang/String;Lscala/collection/immutable/Map;)Lscala/Function1;
        34: aastore
        35: dup
        36: iconst_1
        37: new           #402                // class io/findify/s3mock/route/CopyObject
        40: dup
        41: aload_0
        42: invokevirtual #206                // Method p:()Lio/findify/s3mock/provider/Provider;
        45: invokespecial #403                // Method io/findify/s3mock/route/CopyObject."<init>":(Lio/findify/s3mock/provider/Provider;)V
        48: aload_2
        49: aload         4
        51: invokevirtual #397                // Method akka/http/scaladsl/model/Uri$Path.toString:()Ljava/lang/String;
        54: invokevirtual #406                // Method io/findify/s3mock/route/CopyObject.route:(Ljava/lang/String;Ljava/lang/String;)Lscala/Function1;
        57: aastore
        58: dup
        59: iconst_2
        60: new           #408                // class io/findify/s3mock/route/PutObjectMultipart
        63: dup
        64: aload_0
        65: invokevirtual #206                // Method p:()Lio/findify/s3mock/provider/Provider;
        68: aload_1
        69: invokespecial #411                // Method io/findify/s3mock/route/PutObjectMultipart."<init>":(Lio/findify/s3mock/provider/Provider;Lakka/stream/Materializer;)V
        72: aload_2
        73: aload         4
        75: invokevirtual #397                // Method akka/http/scaladsl/model/Uri$Path.toString:()Ljava/lang/String;
        78: invokevirtual #412                // Method io/findify/s3mock/route/PutObjectMultipart.route:(Ljava/lang/String;Ljava/lang/String;)Lscala/Function1;
        81: aastore
        82: dup
        83: iconst_3
        84: new           #414                // class io/findify/s3mock/route/PutObjectMultipartStart
        87: dup
        88: aload_0
        89: invokevirtual #206                // Method p:()Lio/findify/s3mock/provider/Provider;
        92: invokespecial #415                // Method io/findify/s3mock/route/PutObjectMultipartStart."<init>":(Lio/findify/s3mock/provider/Provider;)V
        95: aload_2
        96: aload         4
        98: invokevirtual #397                // Method akka/http/scaladsl/model/Uri$Path.toString:()Ljava/lang/String;
       101: invokevirtual #416                // Method io/findify/s3mock/route/PutObjectMultipartStart.route:(Ljava/lang/String;Ljava/lang/String;)Lscala/Function1;
       104: aastore
       105: dup
       106: iconst_4
       107: new           #418                // class io/findify/s3mock/route/PutObjectMultipartComplete
       110: dup
       111: aload_0
       112: invokevirtual #206                // Method p:()Lio/findify/s3mock/provider/Provider;
       115: invokespecial #419                // Method io/findify/s3mock/route/PutObjectMultipartComplete."<init>":(Lio/findify/s3mock/provider/Provider;)V
       118: aload_2
       119: aload         4
       121: invokevirtual #397                // Method akka/http/scaladsl/model/Uri$Path.toString:()Ljava/lang/String;
       124: invokevirtual #420                // Method io/findify/s3mock/route/PutObjectMultipartComplete.route:(Ljava/lang/String;Ljava/lang/String;)Lscala/Function1;
       127: aastore
       128: dup
       129: iconst_5
       130: new           #422                // class io/findify/s3mock/route/PutObject
       133: dup
       134: aload_0
       135: invokevirtual #206                // Method p:()Lio/findify/s3mock/provider/Provider;
       138: aload_1
       139: invokespecial #423                // Method io/findify/s3mock/route/PutObject."<init>":(Lio/findify/s3mock/provider/Provider;Lakka/stream/Materializer;)V
       142: aload_2
       143: aload         4
       145: invokevirtual #397                // Method akka/http/scaladsl/model/Uri$Path.toString:()Ljava/lang/String;
       148: invokevirtual #424                // Method io/findify/s3mock/route/PutObject.route:(Ljava/lang/String;Ljava/lang/String;)Lscala/Function1;
       151: aastore
       152: dup
       153: bipush        6
       155: new           #426                // class io/findify/s3mock/route/DeleteObject
       158: dup
       159: aload_0
       160: invokevirtual #206                // Method p:()Lio/findify/s3mock/provider/Provider;
       163: invokespecial #427                // Method io/findify/s3mock/route/DeleteObject."<init>":(Lio/findify/s3mock/provider/Provider;)V
       166: aload_2
       167: aload         4
       169: invokevirtual #397                // Method akka/http/scaladsl/model/Uri$Path.toString:()Ljava/lang/String;
       172: invokevirtual #428                // Method io/findify/s3mock/route/DeleteObject.route:(Ljava/lang/String;Ljava/lang/String;)Lscala/Function1;
       175: aastore
       176: checkcast     #375                // class "[Ljava/lang/Object;"
       179: invokevirtual #379                // Method scala/Predef$.wrapRefArray:([Ljava/lang/Object;)Lscala/collection/mutable/WrappedArray;
       182: invokevirtual #383                // Method akka/http/scaladsl/server/Directives$.concat:(Lscala/collection/Seq;)Lscala/Function1;
       185: areturn
      LocalVariableTable:
        Start  Length  Slot  Name   Signature
            0     186     0 $this   Lio/findify/s3mock/S3Mock;
            0     186     1 mat$1   Lakka/stream/ActorMaterializer;
            0     186     2 bucket$1   Ljava/lang/String;
            0     186     3 params$1   Lscala/collection/immutable/Map;
            0     186     4   key   Lakka/http/scaladsl/model/Uri$Path;
      LineNumberTable:
        line 44: 0
        line 45: 13
        line 46: 37
        line 47: 60
        line 48: 84
        line 49: 107
        line 50: 130
        line 51: 155
    MethodParameters:
      Name                           Flags
      $this                          final synthetic
      mat$1                          final
      bucket$1                       final
      params$1                       final
      key                            final
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
```

Also See: [Fully Dump Result](./javap.md)
Also See: https://github.com/findify/s3mock/blob/6e1a7831529f6e51e37a9928895c2297e4826a07/src/main/scala/io/findify/s3mock/S3Mock.scala#L45-L55

## Full Information

