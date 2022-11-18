all: build
configure:
	@CXX="ccache g++-11" cmake -DCMAKE_EXPORT_COMPILE_COMMANDS=ON -G Ninja ..
c: clean
clean:
	@git clean -d -f -x
build:
	@ninja
r: run
run:
	@./pbrt --gpu --interactive --fullscreen /home/gonsolo/src/bitterli/cornell-box/scene-v4.pbrt
filter:
	@sed -i 's/ --use_fast_math//g' compile_commands.json
	@sed -i 's/ --gpu-architecture=sm_86//g' compile_commands.json
	@sed -i 's/ --forward-unknown-to-host-compiler//g' compile_commands.json
	@sed -i 's/ --extended-lambda//g' compile_commands.json
	@sed -i 's/ --expt-relaxed-constexpr//g' compile_commands.json
	@sed -i 's/ --diag_suppress=virtual_function_decl_hidden//g' compile_commands.json
	@sed -i 's/ --diag_suppress=partial_override//g' compile_commands.json
	@sed -i 's/ --diag_suppress=integer_sign_change//g' compile_commands.json
	@sed -i 's/ --diag_suppress=implicit_return_from_non_void_function//g' compile_commands.json
	@sed -i 's/ --diag_suppress=declared_but_not_referenced//g' compile_commands.json
	@sed -i 's/ -suppress-stack-size-warning//g' compile_commands.json
	@sed -i 's/ -rdc=true//g' compile_commands.json
	@sed -i 's/ -maxrregcount//g' compile_commands.json
	@sed -i 's/ -forward-unknown-to-host-compiler//g' compile_commands.json
	@sed -i -e 's/--use_fast_math //g' compile_commands.json
	@sed -i -e 's/-DPBRT_BUILD_GPU_RENDERER //g' compile_commands.json
.PHONY: all build configure c clean all filter r run
