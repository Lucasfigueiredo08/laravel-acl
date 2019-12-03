<?php

namespace App\Http\Controllers\Painel;

use App\Http\Controllers\Controller;
use App\User;
use Gate;

class UsersController extends Controller {
	private $user;

	public function __construct(User $user) {
		$this->user = $user;
	}

	public function index() {
		$users = $this->user->all();

		if (Gate::denies('user')) {
			return redirect()->back();
		}

		return view('painel.users.index', compact('users'));
	}

	public function roles($id) {
		//RECUPERA O USUARIO

		$user = $this->user->find($id);

		//recuperar roles

		$roles = $user->roles()->get();

		return view('painel.users.roles', compact('user', 'roles'));
	}
}
