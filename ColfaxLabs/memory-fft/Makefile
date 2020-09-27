CXX=icpc
CXXFLAGS=-xMIC-AVX512 -qopenmp -mkl -lmemkind
OPTRPT=-qopt-report=5

default : app


worker.o : worker.cc
	${CXX} -c ${OPTRPT} ${CXXFLAGS} -o "$@" "$<"

app : main.cc worker.o
	${CXX} ${OPTRPT} ${CXXFLAGS} -o "$@" "$<" worker.o

queue : app
	echo 'cd $$PBS_O_WORKDIR ; ./app' | qsub -l nodes=1:flat -l walltime=00:02:00 -N fft

clean :
	rm app worker.o *.optrpt


